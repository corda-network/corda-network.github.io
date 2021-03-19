# Cryptographic Material Policy

## 1 Introduction

The Network Operator must manage all operationally-sensitive cryptographic material in a secure and controlled manner. This
document outlines provisions for secure generation, storage and access control of cryptographic material in relation to
Corda Network. It follows the policies on [Access Control](/policy/access-control) and
[Infrastructure Management](infrastructure-management.md).

## 2 Motivation

The Network Operator manages and controls the certificate authority ("Identity Manager") for all Corda Network environments, with the intention for Corda Network to serve as a global network of legal entities engaging in significant transactions via Corda.

Inappropriate management of the Foundation and Network Operator's cryptographic key material could expose not only the
Foundation but all such participants to major financial and reputational risk. The Foundation therefore recognises the
importance of ensuring that the generation and full-lifecycle management of sensitive cryptographic material is
conducted in a secure and controlled manner.

## 3 Governance

The Network Operator's security team owns the definition of this policy and monitoring compliance with it on an on-going basis. The operations team is accountable for implementation of this policy and maintaining compliance.

## 4 Scope

In the context of this document, cryptographic material refers to any information which may be used to assert ownership
of an identity using cryptographic means. This primarily relates to private ("signing") keys used in public key
cryptography. Identities of relevance to this policy include (but are not limited to) those used for the
Corda Network certificate authority ("Identity Manager").

"Sensitive" cryptographic material refers specifically to cryptographic material of significance such that the Foundation
or Network may be reputationally or operationally impacted by its loss or disclosure to external parties, or into the
public domain. This is typically limited to 'production' contexts, but may also apply to non-production environments
where commitments exist provide secure services to external stakeholders.

## 5 Data Security

All sensitive cryptographic material managed by the Network Operator should be stored on a Hardware Security Module (see 2.2). HSMs used for this purpose shall be tamper-resistant to FIPS 140-2 level 3 or higher.

Under no circumstances shall such sensitive cryptographic material be permitted to exist in an unencrypted (“clear text”)
format outside of an HSM.

All communication between HSMs containing sensitive cryptographic material and other networked devices shall occur via
encrypted sessions, authenticated using an appropriate (e.g. Diffie-Hellman-based) exchange protocol. Sessions will be
configured to expire after a maximum of 15 minutes of inactivity by the user.

To the extent possible, all communications protocols and other functions not essential to production use (e.g. SNMP,
IPV6) shall be disabled.

Devices facilitating authentication with an HSM (e.g. USB smart card readers) shall be stored securely and tracked
using a Physical Assets Register.

### Network security

Network arrangements for HSMs containing sensitive cryptographic material shall provide appropriate firewall-based
segmentation, such that:

- At no point can an HSM receive direct incoming connections from the Internet.
- An HSM can only receive incoming connections from one or more controlled 'management zone' subnets within the local
  area network.
- Outbound connections from an HSM to the internet occurs via a suitable proxy device within a management zone.
- Access is only enabled on specifically configured ports.

All such network arrangements shall be subject to formal change control in accordance with the
[Change Management Policy](/policy/change-management).

### Infrastructure maintenance

Deployment of or changes to HSMs containing sensitive cryptographic material, or their supporting infrastructure,
require controlled deployment procedures governed by the [Deployment Policy](/policy/deployment).

HSMs and all supporting devices (e.g. application servers, management consoles and card readers) constitute assets to
be managed according to the [Inventory Management Policy](/policy/inventory-management).

### Patching and updates

The operations team shall monitor the availability of updates and patches, including (but not limited to):

- HSM firmware updates.
- HSM client software updates.
- OS updates for servers and management consoles.
- Updates to anti-virus software for management consoles.

At a minimum, availability of suitable updates and patches shall be manually checked every 30 days. A structured method
(e.g. recurring calendar invite) should be used to ensure compliance with this schedule.

### Backups

All sensitive cryptographic material shall be subject to regular backups. Backups should be carried out routinely every
7 days, at a minimum. Manual backups should also be initiated before any change in configuration of an HSM.

Backups of sensitive material must be exported from HSMs in an encrypted state and under no circumstances be persisted
in a plain-text form. Backups should be separately encrypted using credentials managed by DevOps.

Backups should be stored on an appropriate cloud platform (e.g. [Egnyte](https://egnyte.com/)) which is approved
for Network Operator corporate use, and which allows for:

- Geo-redundant replication to mitigate risk of loss.
- Historic version retention.
- Restriction of access to authorised individuals (HSM Administrators).
- Access by multiple authorised individuals.

## Access Control

Access to resources containing sensitive cryptographic material follows the [Access Control Policy](/policy/access-control).

Specifically, HSMs containing sensitive cryptographic material shall implement Role-Based Access Control, wherein:

- Any function requires an authenticated user.
- At least 2/n distinct users are required to perform any administrative function (creating users, changing user
  permissions etc.).

The creation and deletion of new user accounts, or changes to roles assigned to users, is subject to formal change
management according to the [Change Management Policy](/policy/change-management).

The rota of users with access to perform both cryptographic and administrative operations shall be actively managed by
the operations team to ensure that:

- No single user is assigned credentials which could undermine the 2/n principle outlined above.
- At any time, at least two individuals have access to credentials required for performing any cryptographic or
  administrative procedure, such that operational continuity is maintained throughout staff absence and rotation.

### User Credentials

Authentication shall require, at a minimum, two-factor authentication (e.g. a smart card and PIN).

Where smart cards or other physical factors are used, these are held under the personal custody of the assigned users
and must not be shared between users.

Assignment of physical factors to users must be tracked using the Physical Assets Register.

PINs must be selected by the individual user to be easily memorable but not guessable. PINs for personal user
credentials must not be shared between users.

PINs should, in principle, be changed on an annual basis.

### Administrative Credentials

DevOps shall manage all shared credentials required for the operation and management of HSMs and related devices,
including (but not limited to):

- BIOS passwords for all devices.
- System account passwords for HSMs and other devices.
- PINs associated with Master Backup Keys (MBKs).
- HSM manufacturer portal login details.

### Password Generation

A strong random password generation tool (e.g. [KeePass](http://keepass.info/)) which includes the injection of
user-generated entropy (e.g. mouse movements/clicks) must be used in the generation of all shared credentials.

Where not otherwise constrained, passwords should be upper-lower-numeric strings with no punctuation or other symbols
and no confusing characters (1, l, O, 0). Administrator passwords should be 20 characters in length; other user
passwords 15 characters.

### Password Storage

Credentials should under no circumstances be persisted in a plain-text form. At a minimum, a password database
(e.g. [KeePass](http://keepass.info/)) implementing AES256-bit or equivalent/greater encryption must be used for
storing all relevant passwords. Credentials used to access this database must be stored separately to the database
itself.

Password databases should be stored on an appropriate cloud platform (e.g. [Egnyte](https://egnyte.com/)) which is
approved for Network Operator corporate use, and which allows for:

- Geo-redundant replication to mitigate risk of loss.
- Historic version retention.
- Restriction of access to authorised individuals (HSM Administrators).
- Access by multiple authorised individuals.

Copies of password databases should not be persisted over long periods to client devices e.g. operations team personal
laptops, management consoles; however, they may be locally downloaded and transiently used before deleting after use.

### Backup Restore ("MBK") Credentials

Credentials ("backup keys") allowing the reconstitution of sensitive cryptographic material on an HSM or other device
shall be managed in such a way that:

- Backup keys are not persisted to any form of online storage.
- Backup keys are not stored in a complete form, but are distributed across multiple media such that a suitable n/m
  policy (e.g. 2:6) is enforced.
- Backup key media are distributed across multiple separate physical locations to ensure redundancy in the event of
  disaster.
- Backup key media are stored in highly secure environments (e.g. safety deposit boxes).
- Backup key media are only accessible by appropriately authorised Network Operator personnel.
- Backup key media are only accessible with explicit authorisation from a member of Network Operator senior management.

## Tamper Inspections

HSMs shall be subject to inspections for evidence of accidental or malicious tampering every 30 days, at a minimum.

The operations team is responsible for leading inspections. All inspections must be witnessed by an appropriate delegate
oversight party on behalf of senior management.

Inspections must be logged. Logs shall be reviewed by the Network Operator security team every 6 months, at a minimum.

## Audit Trail

HSMs containing sensitive cryptographic material will capture and retain a log of all relevant business and system
events. Audit logs captured by this process will be stored in accordance with the data. Security are responsible for
reviewing audit logs from HSMs on a monthly basis.

## Physical Access

Physical access to HSMs containing sensitive cryptographic material will be controlled in such a manner that, at a
minimum, requires one member of the operations team and one member of the Network Operator executive team to secure access.
