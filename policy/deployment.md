|Corda Network Foundation|[Document history]({{ site.github.repository_url }}/blame/master/{{page.path}})|

Deployment Policy
=================

1 Introduction
--------------
This is the policy for the deployment of software components by the Operator onto physical infrastructure for 
Corda Network.

2 Change management
-------------------
All deployment activity shall be undertaken in accordance with change management procedures defined in the 
[Change Management Policy](change-management.md).

In particular:

*   Deployments shall be performed response to an approved Change Request (CR) submitted to the Operator operations team.
*   Deployments should be scheduled to minimize disruption to Corda Network operations.

See the [Change Management Policy](change-management.md) for more information.

3 Deployment procedures
-----------------------
All activity to deploy new infrastructure components must follow a documented procedure. This section specifies the 
requirements for creating and managing deployment procedures.

### Procedure development
The Operations team should maintain standard deployment procedures for common tasks (e.g. deploying a new Notary VM). 
The Operations team may develop new procedures on an ad-hoc basis in response to previously unforeseen scenarios; such 
ad-hoc procedures must still be documented prior to being executed.

Wherever possible, detailed deployment procedures should be developed in a scripted form, compatible the adopted 
automated deployment tool (see below). Scripted deployment procedures should be annotated with suitable comments to 
facilitate review of the document and subsequent auditing by knowledgeable parties. Where a deployment procedure cannot 
be scripted, or includes any manual steps, those manual steps must still be documented in a suitable form which 
facilitates review and audit. 

All deployment procedures must include appropriate controls to validate the expected outcomes of that procedure, and 
define appropriate handling of any exceptions.

Deployment procedures should not, in principle, access any resources outside of the procedure library and deployment 
package staging area (see below), in addition to the deployment target.

### Procedure inventory
All deployment procedures, once documented, should be retained in a code repository and subject to git-based revision 
control.

The Operations team owns this code repository ('deployment procedure library') and is responsible for maintaining the 
content in an organised manner that facilitates efficient identification, execution and review of procedures, as well 
as ensuring it complies with the Data Retention Policy. The Operations team also administers access to this repository. 
In principle, access should be restricted to members of the Operations team team; the Operations team team lead may at 
its own discretion provide temporary access to specific Operator personnel to assist with specific business tasks.

Introduction of new deployment procedures, as well as revisions to existing procedures, must be subject to a four-eyes 
quality review by a suitably qualified individual (typically another member of the Operations team team) prior to being 
committed to the library for subsequent use; the standard git PR review mechanism should be used to enforce this.

### Procedure testing
All deployment procedures must be tested in a non-production environment before use. 

### Procedure execution
All deployment procedures should, in principle, be consciously initiated by a member of the Operations team team.

Auditable evidence of the execution of all deployment procedures must be captured and retained (see Data Retention 
Policy).

4 Tooling
---------
Wherever possible, deployment procedures shall be executed via an automation tool or combination of tools. The 
Operations team is responsible for selecting an appropriate tool, or combination of tools, for each element of a 
deployment procedure requiring automation. The default preferred tools for each activity are listed below; these should 
be used for all deployment procedures in the absence of technical obstacles.

The Operations team may, at its discretion, select an alternative tool to perform a given task where the default tool 
is determined to be unfit for purpose. The rationale for using alternative tooling should be documented within the 
associated deployment procedure(s).

*   Overall deployment operation: [Ansible](https://www.ansible.com/)
*   Code build & packaging: Gradle
*   Cloud infrastructure provisioning: Terraform

The Operations team is responsible for ensuring that all tools used in deployment procedures are themselves updated, 
and that the testing of the deployment process traps for any version compatibility issues between deployment tools and 
the software being deployed.

5 Packages
----------
All software components must be appropriately packaged prior to deployment. 

The Operations team is responsible for selecting an appropriate format for each package. This format should be 
consistent from one version to the next, in the absence of a specific technical or business benefit being achieved by 
updating the format. Packages for components with similar deployment requirements (e.g. notary components and doorman 
components both being JVM-based) should adopt a consistent package format.

Packages should follow a consistent naming convention which facilitates identification and subsequent review.

### Staging repository
All deployment packages should be uploaded to a staging repository prior to deployment. The staging repository is on 
[Maven Artifactory](https://www.jfrog.com/confluence/display/RTF/Maven+Repository).

The Operations team owns this staging repository and are responsible for maintaining the content in an organised manner 
that facilitates efficient identification, execution and review of packages, as well as ensuring it complies with the 
Data Retention Policy. Operations team also administer access to this repository. In principle, access should be 
restricted to members of the Operations team team; the Operations team team lead may at its discretion provide 
limited, temporary access to specific Operator personnel to assist with specific business tasks.

### Package signing
There is no stipulation for packages to be signed or signatures validated prior to deployment.