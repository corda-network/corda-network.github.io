|Corda Network Foundation|[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})|

Trust Root Generation
=====================

The generation of the long-lived trust root for Corda Network required a level of ceremony, witnessing and 
memorialisation that was met through a highly-scripted and secure event held at the R3 offices at 2 London Wall, 
London, UK on Friday 14th September 2018. The ceremony required extensive preparation, advice and guidance from both 
KPMG in 2017 and Schellman in 2018, and included 7 independent witnesses from global banks and R3's partner program. The 
total expenditure was more than one year of effort, and significant financial cost, in order to deliver long-term 
trust.

The full script for the event and other supporting artifacts are found via the links and attachments below.

The root key material generated is held in offline secure locations, and the subordinate key material held on production 
HSMs.

Certificate Policy
------------------
[Current version](certificate-policy.md) is v12 - this should be updated to "issue" before network launch.

Certification Practices Statement
---------------------------------
[Current version](certificate-practices.md) is v09 - this should be updated to "issue" before network launch. 

Certificates
------------
The certificate bundle (in JKS format) is the most likely to be used. The remaining details and formats are included 
for reference and to harmonise with other Certificate Authorities.

|Name                          |Public Key      |Fingerprint                                                |Valid Until  |Links|
|------------------------------|----------------|-----------------------------------------------------------|-------------|-----|
|Corda Network Root Certificate|ECC-256, SHA-256|44:30:BE:62:A8:95:4B:13:03:5A:D3:C4:63:45:6E:9C:F1:1C:E4:65|Jan 18, 2038 |     |
|Corda Network Authority CNA1  |ECC-256, SHA-256|A9:85:9F:69:4A:BF:06:00:3F:92:39:8B:D6:91:E4:AA:D0:02:ED:F5|Jan 18, 2038 |     |
|Corda Network Authority CNA2  |ECC-256, SHA-256|DC:22:4B:27:06:12:C1:23:E1:34:B1:64:22:95:17:09:22:E4:B9:A4|Jan 18, 2038 |     |
|Corda Network Authority CNA3  |ECC-256, SHA-256|EB:3F:58:3C:DA:0A:40:6F:F8:6E:49:9A:22:3F:8C:19:D5:8F:A0:88|Jan 18, 2038 |     |
|Corda Network Authority CNA4  |ECC-256, SHA-256|78:1D:2D:23:54:A5:8E:7A:B5:ED:A1:FE:08:D0:8B:4E:F0:D6:8B:CE|Jan 18, 2038 |     |
|Corda Network Authority CNA5  |ECC-256, SHA-256|7E:B3:9D:A4:D9:ED:F4:B4:86:06:79:6B:FE:F8:2A:7B:9C:C9:0E:97|Jan 18, 2038 |     |
|Corda Network Authority CNA6  |ECC-256, SHA-256|2A:F4:08:90:73:CB:4F:14:B2:93:7A:CB:93:5A:6F:91:45:45:27:EB|Jan 18, 2038 |     |
|Corda Network Authority CNA7  |ECC-256, SHA-256|82:40:F4:0E:A3:84:24:5C:70:23:40:2F:EE:26:32:6D:AA:0E:C4:BE|Jan 18, 2038 |     |
|Corda Network Authority CNA8  |ECC-256, SHA-256|41:67:90:E4:B2:EA:D8:E9:B5:39:51:91:31:8C:D5:3C:C9:67:A0:3B|Jan 18, 2038 |     |


Service Auditor's summary letter
--------------------------------
[Letter](root-key-ceremony-witness-summary-letter.pdf) from the service auditor, Schellman and Company, LLC. 

Ceremony script
---------------
The original version of the script is a blank copy of the script used during the day. The internal witnesses annotated 
script records witness signatures, timings and deviations from the script and other observations.

This is the [Original Script](original-script-v10.pdf).

This is the [Internal Witnesses' annotated script](witness-annotated-script.pdf).

HSM initialisation script
-------------------------
The root and subordinate HSMs were initialized the night before the ceremony. The process was overseen and witnessed by 
the Ceremony Administrator. See the [CA annotated HSM initialisation script](ca-annotated-hsm-initialisation-script.pdf).

Ceremony Video
--------------
Extensive video recordings were made of the ceremony. The originals are not uploaded here, due to a combination of size 
and format constraints. Versions rendered to a manageable size have been uploaded to YouTube. The links below will take you 
there.

The playlist for [Camera 1](https://www.youtube.com/playlist?list=PLi1PppB3-YrW7i3-nOBAE8Maf-EW_kPqx) shows a view of 
the participants in the ceremony.

The playlist for [Camera 2](https://www.youtube.com/playlist?list=PLi1PppB3-YrWGObJ6BIaSU7PnQ_7jlC5t) shows a view of 
the entire room from behind the ceremony witness seating area. 

The Cameras were set to record at 1080p, however the output does not 
appear to reflect this.  Each 20 minute segment is approximately 500MB.

[Video Capture](https://www.youtube.com/playlist?list=PLi1PppB3-YrWvg2IQTZnscqbL50a9E783) shows the output from the 
HSM administration machine that used by the Ceremony Administrator to interact with the HSMs during the ceremony. These 
appear to occupy approximately 724 MB per hour of recorded video at 720p.

HSM management computer screen log
----------------------------------
The output from the HSM management machine was captured using the 'script' utility. There are two copies of the log file:

See  the [original log complete with control characters](original-script-with-control-characters.log). There is a 
SHA fingerprint available for for this file (e66a4c79e2ba4a9a12ee7ea7d28af14d1842d6f18ce203da445b194ce80df097). A 
[processed version of the log](original-script-processed.log) is available (which does not have a fingerprint available, 
but which is easier to read, as it does not have embedded control characters).

HSM Logs
--------
Logs from HSMs and SHA256 fingerprints for the same, calculated on the HMS management computer at the time they were 
exported.

### Root HSM (HSM1)
[HSM Log](hsm01_audit.log) [SHA 256](hsm01_audit.log.sha256.txt)

[CSLAN Log](hsm01_cslan.log) [SHA 256](hsm01_cslan.log.sha256.txt)

### Subordinate HSM (HSM2)
[HSM Log](hsm02_audit.log) [SHA 256](hsm02_audit.log.sha256.txt)

[CSLAN Log](hsm02_cslan.log) [SHA 256](hsm02_cslan.log.sha256.txt)

HSM management machine ISO image
--------------------------------

The ISO image for HSM management machine is downloadable from cloud storage, due to the size of files. The ISO is at 
[tcn-rkg-2018-09-13-09.iso](https://r3share.mohso.com/dl/x5ZRISCR0P/tcn-rkg-2018-09-13-09.iso_) and the corresponding 
checksum is at [SHA checksum](https://r3share.mohso.com/dl/9YB0MlWQvk/SHASUM_). 