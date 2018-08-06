---
layout: default
title: Data & Security Policies
---

This is a policy  applied to security and data protection supplied by the Hourfleet platform for data that is managed on behalf of a Hourfleet network operator.

# Overview 

The Hourfleet platform is composed of a number of HTTP services and worker processes hosted in the cloud. Hourfleet's customers and their end-users, as well as devices, applications and user agents send data over the internet by using any HTTP client. 

All data is confidential, and is encrypted end to end in transit over secure TLS protocol using HTTPS. 

All data that flows between any client and Hourfleet is destined either for the use of the Hourfleet platform (eg. for configuration or auditing purposes) or for the use of each tenant on the Hourfleet platform (eg. car sharing or customer data).

Data bound for use by any tenant is stored in a dedicated services, in one or more geographical regions of the Microsoft Azure Cloud.

# Data Protection

### Data Stores

Each Hourfleet tenant has a *dedicated* data store (Azure Storage Account) provisioned for it (in the Microsoft Azure cloud) in a geographic region of choice. This means that each tenant on the Hourfleet platform has a physically separated data store that is secured by unique access keys only accessible by that tenant, in order to limit any security breaches of any single tenant to that tenant.

>  Azure Table Storage, Azure Queue Storage and Azure Blob Storage are not centralized databases like say: SQL Server, but rather a distributed data service, that maintains very high scalability and availability.

Typically, the primary region for the tenancy is located closest to the main end-users for that tenancy. The choice is largely influenced by reducing the network latency between the end users agents and the Hourfleet platform.

The data stored in the primary region is replicated in a secondary region, generally close to the primary region. See Azure documentation for more details on [GRS cross-regional replication](https://docs.microsoft.com/en-us/azure/storage/common/storage-redundancy-grs).

All access to all data stored in any Azure Storage Account is securely encrypted via HTTPS, and limited to direct access by only components in the Hourfleet architecture. Access Keys to this storage account are also stored in physically separate key vaults. See [Secrets](#Secrets) below.

All transactional data is stored in these Data Stores.

### Caching

Hourfleet uses numerous caches at various layers in its architecture for storing a variety of transient data, that typically decays with time, and is periodically updated.

There is a single dedicated in-memory cache provider (Redis Server) per geographic region, shared by all tenants in residence in that specific region.

All access to all data stored in Redis is securely encrypted via HTTPS, and limited to direct access by only components in the Hourfleet architecture. Access Keys to this caching service are also stored in physically separate key vaults. See [Secrets](#Secrets) below.

### Configuration

Hourfleet manages a vast collection of configuration for numerous tenants in a single deployment in a single geographic region. It manages the separate configuration of each tenant on the platform with the aid of a collection of configuration for the whole platform.

These configuration sets are stored in a separate data store dedicated to the Hourfleet platform only. There is no access to this store from any tenant on the platform.

All access to all data stored in this dedicated Azure Storage Account is securely encrypted via HTTPS, and limited to direct access by only components in the Hourfleet architecture. Access Keys to this storage account are also stored in a platform dedicated Azure Key Vault. See [Secrets](#Secrets) below.

### Secrets

Hourfleet maintains a vast collection of confidential configuration for the platform and for numerous tenants in a single deployment in a single geographic region. It manages secure access and connections to numerous 3rd party services, including those within its own internal architecture (i.e. data stores, caches, etc). 

As such, it has to manage numerous secrets (e.g. account credentials),  in order to protect the confidentiality of its tenants and any data flowing to and from the Platform.

Hourfleet stores all secrets in dedicated Azure Key Vaults. Data stored in an Azure Key Vault is replicated in a secondary region. See [Azure Key Vault Redundancy](https://docs.microsoft.com/en-us/azure/key-vault/key-vault-disaster-recovery-guidance) for more information.

Each tenant within a geographic region has provisioned for it a *dedicated* Azure Key Vault in order to limit any security breaches of any single tenant to that tenant. There is also a dedicated Key Vault for the platforms own exclusive use.

All access to Azure Key Vault is secured using HTTPS. All access to all secrets by Hourfleet is limited to read-only access to all secrets and keys, from a dedicated account specific to the specific tenant.

### Access to Transactional Data

All transactional data (i.e user accounts, audits, car sharing data) is permanently stored in dedicated and separate Azure storage accounts for each tenant in any geographic region. That data store is secured by protected access keys.

Access to these stores is necessary for the Hourfleet platform to operate.

Read-only access to these stores is offered to individual tenants upon written request.

## Data Retention

Upon the creation of an Hourfleet tenancy, various Azure components are automatically provisioned and configured. Each of these components has a separate data retention policy applied to it.

Platform Data - TODO

Tenant Transactional Data - TODO

Tenant Transient Data (Cached Data) - TODO

## Personally Identifiable Information (PII)

Hourfleet captures, transports and stores PII data in various forms.

Examples of PII data are:

* Email addresses
* Mobile phone numbers
* Drivers licenses
* Photos
* Bank account numbers
* Certificates of road worthiness
* Car license number plates and VIN numbers

All PII data is captured and transported securely, and stored in secure data repositories specific to the tenant where the data was captured.

Hourfleet must sanitize all PII data returned from all API responses so that this confidential infromation is not inadvertantly revealed unintentionally to any external party, except the owner of the PII data, or a trusted recipient of that data. 

For example, if a user requests their own profile from Hourfleet, the response from Hourfleet may contain certain PII data of theirs (i.e. their email address). However, if a user requests another users' profile, all unnecessary PII data is removed from the response. 

> Note: In some cases, certain PII data must be shared between certain users in certain circumstances. For example, the email address and phone number of a car owner might need to be shared with the borrower of their car for the purposes of directly contacting them in an emergency situation while using the car. Hourfleet, ensures that this data is kept confidential between these parties. 

### PCI Compliance

Hourfleet is not [Payment Card Industry Data Security Standards](https://www.pcisecuritystandards.org/security_standards) (PCI DSS) compliant.

Hourfleet **does not** directly capture nor store credit card information provided by any user.

Hourfleet integrates directly with and delegates to trusted payment providers such as [Stripe.com](www.stripe.com) to gather and store credit card information on behalf of all users of the platform.


# Auditing

The Hourfleet platform has been designed for operational monitoring, with a built in capability for detailed diagnostics, and reporting.

All activities in the Hourfleet platform that result in any change in state of *any* data is logged permanently.

Many business critical activities (such as: registering new users, booking cars, etc.) are also audited separately and stored historically to prevent future repudiation by teh initiating party. 

Numerous activities with any interest in security or performance impact are also measured. Metrics are also collected for measuring usage, for A->B testing and other reasons.

Any faults or crashes that are experienced as also logged permanently.

Depending on the source of the information, this logged data is either stored in the tenancy storage where the activity took place, or in platform storage (i.e. crash reports, performance counters etc.).

TODO

- Independent Assessments results or certifications. 

  * Arrangements for 3rd party agreed auditing?

# Authentication and Administration



TODO

- Authentication
- Account Provisioning
- Account Access Termination
- Passwords Policy - eg. length, complexity, reuse etc.
- Account Lockout Policy
- Password Reset Policy

# Disaster Recovery

* DR processes
  * Storage outages: https://docs.microsoft.com/en-us/azure/storage/common/storage-disaster-recovery-guidance
  * Redis: its a cache, if it goes down, the data can be rebuilt any time after it comes back up. The impact is only to performance of the system.
  * Azure Key Vault outages: https://docs.microsoft.com/en-us/azure/key-vault/key-vault-disaster-recovery-guidance
* Backups
* SLA, RTO and RPO



# Incident Response

* Notification process of security incidents/breaches
* The process, the SLA



# References

Terms of Service

Privacy Policy

Service Level Agreement
