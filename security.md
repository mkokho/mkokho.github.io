# Security Pillar 

Design principles:
 - Implement a strong identity foundation
   - Principle of least privilege
   - Enforce separation of duties
   - Centralize privilege management
   - Reduce usage of long-term credentials
 - Enable tracebility
 - Apply security at all levels
 - Automate by managing security as a code
 - Protect data in transit and at rest
 - Keep people away from data
 - Prepare for security events

Areas
 - [Identity and access management](#identity-and-access-management)
 - [Detective controls](#detective-controls)
 - [Infrastructure protection](#infrastructure-protection)
 - [Data protection](#data-protection)
 - [Incident response](#incident-response)

## Identity and access management
Ensures that only authorized and authenticated principals (users, groups, services, roles) are able to access your resources, and only in a manner that you intend.

#### Implementing strong credential management
 - Every interaction with AWS is authenticated
 - Root account has access to all resources, so it must be protected with MFA and has no access keys
 - IAM users constrained by appropriate policies and MFA are for everyday tasks
 - IAM roles should be used to grant permissions thus forcing IAM users to assume role with enforcement of MFA
 - Use AWS STS to give permissions to the cloud services (instances, services, tasks)
 - Use Managed policies instead of Inline policies
 - Rotate credentials
 - Use policy conditions for extra security
 - Monitor activity

#### Fine-grained authorization
Principle of least privilege limits the potential impact of inappropriate use of valid credentials. It enforces separation of duties for oversight and governance. Use IAM roles and policies to implement fine-grained authorization.


## Detective controls
Detective controls are an essential part of genernance frameworks. They are used to identify a potential thread an incident.

 - Capture and analyze logs
 - AWS CloudTrail captures activity in AWS
   - AWS CloiudWatch to collect application-based logging
   - AWS GuardDuty is a managed threat detection service
   - AWS Athena to analyze logs stored in S3 buckets
 - Integrate auditing with notifications
   - AWS Config to detect changes in configured services
   - AWS SNS to send notifications
   - AWS Inspector to find known vulnerabilitues and exposures (CVEs)


## Infrastructure protection
Methodologies to ensure that systems and services are protected against unintended and unathorized access and potential vulnerabilities.

 - Protecting network and host-level boundaries
   - NACL for subnets. It is statelss so both inbound and outbound rules need to be defined.
   - Security groups as statefull firewall for hosts and services.
   - Try to use non-overlapping IP addresses for the VPC.
 - System Security Configuration and Maintenance 
   - Automate deployment and maintanance to reduce the attach surface
   - AWS Systems Manager to define, maintain, and query operating system configuration
   - AWS Systems Manager Patch Manager to patch systems
   - AWS Inspector to identify vulnerabilities
 - Enforcing Service-Level Protection
   - S3 has bucket policies that define access levels to buckets/objects
   - KMS has policies to define administrators and users of the keys
 

## Data protection
 - Data classisfication to create foundation for approriate access levels
   - balance usability vs access
   - reduce human access to data
   - ensure access from trusted network
   - require access to decryption keys
   - use dashboards and automated reporting
 - Encryption/tokenization
  - protecting data at rest
  - protecting data in transit
  - Backups/replication/recovery 
 - to protect against deletion or destruction 

## Incident response
Maintaned processes helps to effectively respond and mitigate the potential impacts of security icidents.

- Use tags that helps identify owners, security levels, criticality, and other properties of impacted workloads
- Determine access the team member needs ahed of time
- Use AWS APIs to automate tasks performed during an incident and investigations
- Create snapshots that provide impacted system "as-is" to the forensics team
- Create trusted environment to conduct deeper investigations


