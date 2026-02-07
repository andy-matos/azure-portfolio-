# Lab 02 – Azure Storage Account

## Objective

Deploy and configure an Azure Storage Account following best practices for performance, security, and cost efficiency.

## Architecture Overview

- Subscription: Azure subscription 1
- Resource Group: rg-lab-az900
- Region: East US
- Storage Account Type: Standard
- Replication: Locally Redundant Storage (LRS)
- Access Tier: Hot

## Configuration Details

- Performance: Standard
- Replication: LRS
- Large file shares: Enabled
- Hierarchical namespace: Disabled
- SFTP: Disabled
- NFS v3: Disabled

## Security Settings

- Secure transfer required: Enabled
- Minimum TLS version: 1.2
- Blob anonymous access: Disabled
- Storage account key access: Enabled
- Public network access: Enabled (All networks)

## Data Protection

- Blob soft delete: Enabled (7 days)
- Container soft delete: Enabled (7 days)
- File share soft delete: Enabled (7 days)
- Versioning: Disabled
- Point-in-time restore: Disabled

## Encryption

- Encryption type: Microsoft-managed keys (MMK)
- Infrastructure encryption: Disabled

## What I Learned

- Differences between LRS, GRS, and RA-GRS
- How to configure storage security options
- Importance of soft delete in data protection
- Cost implications of replication types

## Cost Considerations

LRS was selected to minimize costs while maintaining local redundancy within a single Azure region.
