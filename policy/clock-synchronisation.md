|Corda Network Foundation|[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})|

Clock Synchronisation Policy
============================

1 Proposed policy
-----------------
Members of a notary cluster in the Corda network must maintain clock synchronisation to leap-smeared UTC within a 
tolerance of 100 milliseconds. Leap seconds are not visible, as during a leap the length of each second is adjusted 
from noon-to-noon, bringing Corda time temporarily out of alignment with UTC for a 24 hour period centred around the 
leap event. Please note that Corda uses the proleptic Gregorian calendar - this is a protocol level rule and is not 
subject to zone policy.

Nodes that are not taking part in a notary may synchronise their clocks to the specified timeline, however they are not 
required to by policy. Nodes that are offering oracle services to other nodes are encouraged to synchronise to the same 
degree as notary nodes, but again, are not required to by policy.

The zone operator will announce a reference timezone data file (tzdata). This announcement is advisory: changes to the 
tzdata do not change network parameters and thus do not trigger a governance event. However, using the announced 
tzdata is recommended to keep nodes in alignment. The exact mechanism used for announcing tzdata epochs is a part of the 
Corda protocol and not subject to zone policy.

To ensure consensus, tzdata files are expected to be attached to transactions that require timezone calculations such 
that the standard Java date/time APIs will load the attached data within the deterministic sandbox and not from the JVM 
or operating system tzdata source. Therefore old transactions will be verified against old tzdata snapshots and timezone 
calculations will be fully deterministic.

New tzdata epochs will start being announced by the zone operator within 10 UK working days of an upstream release. 
Upstream is defined as being the IANA nominated maintainer of global timezone data. At the time of writing the maintainer 
is Paul Eggert.

As the tzdata announcement and attachment mechanisms are not implemented in Corda at this time, this proposed policy is 
forward looking. It will activate no more than 90 days after the release of a new version of Corda that supports tzdata 
announcement.

2 Rationale
-----------
### Leap second handling
UTC is the global reference timezone. From an engineering perspective it has many desirable properties, for example, it 
doesn't change due to political decisions and it doesn't have daylight savings adjustments. It is also calculable using 
a simple offset in seconds from International Atomic Time (TIA), a feed of which is available via GPS satellites and 
long wave radio.

UTC also has one very undesirable property which is that at arbitrary moments an additional second is inserted into the 
timeline. These leap seconds are intended to keep UTC in sync with slight distortions in the rotational velocity of the 
Earth and are what cause the offset from TIA. They are decided on roughly six months in advance by the International 
Earth Rotation and Reference Systems Service, based on measurements made using astronomical interferometry. Upcoming 
leap seconds are announced via timecode broadcasts and NTP responses.

A common way to adjust clocks for leap seconds is to rewind the clock by a second at midnight. Unsurprisingly many 
developers write software on the assumption that time never goes backwards. The 2012 leap second event caused outages 
at major websites. In addition, because leap seconds are rare and therefore very hard to test, there is a long history 
of bugs in the implementation of leap second announcements. It has been reported that the global NTP pool has never 
successfully coordinated setting the leap second announcements in their time responses, and in at least one case there 
was a suspicious announcement by some pool servers that wasn't real. The problems caused by leap seconds are so 
extensive that there are now widespread calls to effectively abolish UTC by synchronising it with International Atomic 
Time once and for all, eliminating any further leap second adjustments.

As a consequence of all this, major network operators have started converging on a different approach in which the 
length of each second is lengthened or shortened around the time of a leap second event. Thus time always proceeds 
monotonically and software never has to handle time going backwards. This is called leap smearing and is becoming the 
canonical way to handle leap second events. Corda should follow this trend and insulate app developers from having to 
think about leap seconds.

Unfortunately there is no universally agreed way to handle leap seconds. Google and Amazon have converged on UTC with a 
24 hour smear noon-to-noon. Azure and the global NTP pool relies on rewinding the clock at midnight. Bloomberg uses a 
linear 2000 second smear after midnight. The java.time API introduced in Java 8 specifies a 1000 second smear before 
midnight, however, Java doesn’t actually implement this and relies on a pre-smeared time source to be provided by the OS. 
The basic principle that time does not go backwards however is a part of the Java specification.

We propose using the Google and Amazon smear. Google run public NTP servers synchronised to their own atomic clocks 
which implement this smear, and it can be implemented locally by using the NTPsec or Red Hat's Crony daemon with the 
correct configuration parameters. Note that global NTP pool servers do not and will likely never implement leap 
smearing, thus to sync machines to smeared time without using Google's public NTP pool requires you to run your own 
NTP relay configured to apply the smear. An acceptable way for notary nodes to synchronise to leap smeared time is 
therefore to simply do an NTP sync to time.google.com - this is a global load balanced service with atomic clocks in 
North America, Europe and Asia usable by anyone for free. Amazon provide an identical NTP feed inside AWS.
Synchronisation tolerance
Tolerance is defined as 100 milliseconds. This is generous - NTP is capable of synchronising to a reference clock with 
a millisecond or less of drift when the clock is within the same data-centre. However, the notary clocks are intended for 
verifying the time window put into Corda transactions. In practice the latency involved with building, digitally signing 
and submitting a transaction to a notary member will dominate total latency and thus very tight clock sync is unlikely 
to be widely exploited by users. It would require very precise measurements of tx build time and very little drift but 
e.g. Linux kernel target timeslicing latency is 6 msec by default, so if tolerance was 10 msec it'd be unlikely many 
apps could really use it without expert tuning.

### Interaction with MiFiD 2
The EU MiFiD2 regulation imposes certain synchronisation tolerances on 'trading venues'. The Corda network is probably 
not a trading venue in the classical sense and is not intended to run a high-traffic centralised market infrastructure 
directly (perhaps OTC markets are a better fit). See the section "Market infrastructure" in the tech white paper for 
details on how to integrate CorDapps with a centralised order book.

The regulation specifies that the "act of concluding negotiated transactions" requires a tolerance and granularity of 
1 second. This seems to describe what Corda is most likely to be used for. Tolerance of 100 milliseconds easily fits 
this.

In the event that the Corda network may be classified as a 'trading venue' under EU jurisdiction, a governance event 
may be required to bring the synchronisation tolerance down to 1 millisecond. As notarisation is almost sure to have a 
latency of > 1 millisecond the microsecond granularity requirements of MiFiD2 will not be triggered.

### Which nodes must synchronise
The policy specifies no clock sync policies for non-notary nodes. Notaries verify that their local clock is reading a 
time within the specified time window on a transaction (which is optional and can be open-ended) and they only sign if 
the time matches. In a BFT fault tolerant notary, a node that drifts out of alignment with the rest may refuse to sign 
a transaction that the others would sign - this is treated as a fault and the BFT algorithms will automatically work 
around it.

Due to the complexities inherent in synchronising to leap-smeared UTC (non default NTP setups etc), other types of 
nodes may use arbitrary clock synchronisation systems including no synchronisation. If such nodes are building 
transactions that use time windows they may experience notarisation failures if their drift becomes greater than the 
size of the window. Some use cases may not require transaction timestamps at all and imposing arduous sync requirements 
on those nodes would be unnecessary.

3 Time zone data
----------------
In an ideal world people would tell the time using nanoseconds since the UNIX epoch, like all good programmers do.

In the real world business agreements specify times and dates in local timezones. Those timezone definitions may 
change at short notice due to political decisions, adjust for daylight savings, skip days, be offsets from GMT in 
half-hours instead of hours, specify dates using "years in the current reign of the Emperor" and many other 
inconvenient things.
If you haven't yet encountered the myriad ways the world tries to collectively stab programmers in the back using 
timezones this entertaining video goes into the details.
As Corda is designed to bring different entities into agreement on the state of business affairs, agreement on how to 
interpret timezones is required. The Corda attachments feature is ideal for this and as part of integrating the 
Deterministic JVM work we will look at loading timezone data from attachments. That takes care of "what set of 
timezones were in effect when this transaction was made" but doesn't help you with actually building new transactions. 
This should be a feature of the platform and the zone operator can act as an oracle for this data, as it simply involves 
propagating IANA tzdata across the network.

4 Possible future evolutions
----------------------------
1. Notary clock sync may be made more aggressive to enable "trading venue" classifications under MiFiD 2.
2. tzdata distribution endpoints may be specified.
3. NTP's peer to peer mode and time signing features may be researched as a way to spread a secure time feed through 
the peer-to-peer network, using either clubs or as part of the peer handshaking mechanism.