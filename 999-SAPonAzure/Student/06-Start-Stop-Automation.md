# Challenge 6: SAP start stop automation

[< Previous Challenge](./05-PowerApps.md) - **[Home](../README.md)** - [Next Challenge >](./07-PowerQuery.md)

## Introduction

Mango Inc is looking to optimize the cost of SAP landscape and exploring ways to do that. They're leaning towards getting Reserves Instances (RI) for all production systems and would like to save cost on non-production (sandboxes, project systems, etc.) systems by not operating those during non-business hours. This solution helps them achieve that either using automation tools or schedule based


## Description

The goal of this solution is to facilitate a controlled shutdown & startup of SAP systems, which is a common mechanism to save costs for non Reserved Instances (RI) VMs in Azure.

**Note**: VMs must be deallocated for Azure charges to stop and that's facilitated by scripts

This flexible solution enables (using Azure automation, Azure Tags, Scripting, and PowerShell runbooks):

- Start & Stop of your SAP application servers, central services, database, and corrosponding VMs
- Optionally convert Premium Managed Disks to Standard during the stop procedure, and back to Premium during the start procedure, thus saving cost storage as well  

SAP systems start and stop is done gracefully (using SAP native commands), allowing SAP users and batch jobs to finish (with timeout) minimizing downtime impact. 

## Success Criteria

- Create Azure Automation account
- Tag all the VMs for the **SID** in place
- List the SID to ensure all the systems were tagged correctly
- Execute runbook manually to stop systems
- Schedule the runbook to start the systems
- (Optional) Restrict access to runbooks to an individual user
