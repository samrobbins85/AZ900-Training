# Module 3 - Security, Privacy, Complacency and Trust

## Defence in depth

- Multiple levels of protection
- Attacks against one layer are isolated from subsequent layers

## Shared Security

- Security becomes a shared concern between cloud providers and customers
- Security of anything managed by Microsoft is their responsibility

## Identify and Access

Authentication - Azure AD

- Establish an identity
- Challenges access for credentials

Authorisation - Role based access control

- Prove what you can do

### Azure AD

- Authentication
- Single sign on
- Application management
- B2B
- B2C
- Device management - Can a computer access it?

AD on prem

- LDAP
- Kerberos for Auth
- No federation service

Azure AD

- Common protocols
- Common APIs
- SAML, Open Federationm OpenID for Authentication
- OAuth for Authorisation
- Multi factor Authentication
  - Something you know
  - Something you are
  - Something you possess

Can set up one sign on with Azure AD to sign into AWS if using a dual cloud solution

## Securing Network Connectivity

Perimeter layer protects your network boundaries

Networking layer only permits traffic to pass between networked resources

Azure Firewall - Stateful Managed Firewall

### DDoS

Basic service good for most

Standard service tier adds mitigation tuned to protect network resources

### Network Security Groups

- Inside of Azure
- Filtering traffic
- Source
  - IP Address Range
  - Service tag - Range of networks inside and outside Azure
  - Application security group
- Destination
  - IP Address
  - Virtual Network
  - Application security group
- Priority determines which rule should be applied based on which has the highest priority number
- At lowest priority is all deny so have to specify allowed traffic
- Network Watcher
  - IP flow verify allows you to do a ping within Azure to check if you can get between nodes
  - Next Hop - Allows you to do traceroute
- Application security groups allows you to group computers by name

### Security Center

- Detect, Assess and Diagnose problems

### Key Vault

- Keys can't be reset or recovered
- Access via APIs for developers

### Azure information protection

- Classifies and protects information based on labels
- Automatically classify emails with credit card information in etc

### Advanced Threat Protection

- Solution to identify, detect and investigate advanced threats
- Sensors to detect unusual behaviour and report it
- Uses machine learning

## Governance

### Azure policy

- Stay compliant with corporate policy
- Allow IT to govern how things are created, set virtual machines with certain regions etc.

#### Implementing

1. Create policy definition
2. Apply definition to resources

#### Policy initiative

- A collection of policies
- Apply initiative to the scope you want to

### Role based Access Control

- Fine grained access management
- Govern authorisation
- How permissions are granted in the organisation
- Groups of users get roles, these roles have rights and permissions
- Highly specific roles given
- Roles
  - Owner - Change rules of access
  - Contributor - Everything else
  - Reader - Just read

Can specify in terms of

- Subscription
- Resource Group
- Resource

### Resource Locks

- Prevent accidental deletion of resource groups
- ReadOnly Lock - Can't delete, only read so can't stop VM etc. VM itself can be edited, just that the azure properties can't be changes

### Blueprints

- Combine Templates, Policies and Devops
- Subscriptions with resource control

### Subscription governance

- Billing
- Access Control
- Subscription Limits

### Tags

- Control and monitor resources
- Mainly used for billing, allow to charge to specific department
- Use for a project to know how much a project is costing you

### Azure Monitor

- Collect metrics and logs
- Azure application insights - show what line of code is running slow
- Action group - Send notification, run scripts etc. Useful for increasing size of VM under high load

### Azure Service Health

- Global azure problems
- Allows you to understand if the problem is you or Microsoft
- Get status on issue
- Get root cause analysis

### Azure Advisor

- Recommend changes you could make
- Follow Microsoft best practices
- Need to ensure recommendation follow internal compliance

## Privacy Compliance and Data Protection Standards

### Azure Trust Center

- Understand what compliance is provided
- Need to look at in scope services, only some will have the compliance. E.g. some things only on Azure Government

### Azure Government Services

- Often in separate datacenters
- Can't cross information into Azure Commercial

### Azure China

- Access via 21Vianet
