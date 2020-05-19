---
title: Cost optimisation checklist | Microsoft Docs
description: Discover the possible cost optimisation.
author: sepenet
ms.reviewer: sepenet
tags: billing
ms.service: cost-management-billing
ms.topic: conceptual
ms.date: 05/14/2020
ms.author: sepenet
---

# Cost optimisation check list 


## Checklist 
|#|Guidance  |Cost Optimisation Impact  |Complexity to implement |
|-|---------|---------|---------|
|1|Purchase **Azure Reservation**, for VMs, Redis cache, Managed DBs, app Service, ...,  Purchase **Reserve Capacity**  Storage, Tier for Log Analytics, Sentinel, ...|HIGH|MEDIUM|
|2|Microsoft workloads : AHUB + Dev&Test subscriptions , SQL : Developer License/Managed Instances|HIGH|LOW|
|3|Rightsizing VMs / Upgrade instances to the latest generation, B-Series|MEDIUM|MEDIUM|
|4|Terminate zombie resources: Delete unused VMs, Delete unattached storage volumes, Release unattached Elastic IP addresses|MEDIUM|MEDIUM|
|5|Scheduling on/off times|HIGH|MEDIUM|
|6|Use Spot Instances|MEDIUM|LOW|
|7|Move infrequently-accessed data to lower cost tiers (cold storage)|LOW|MEDIUM|
|8|Standard SSD vs Premium SSD|MEDIUM|HIGH|
|9|PaaS services : Use PaaS services to decrease mgmt costs (Scale Up/Down, Stop/Start)|MEDIUM|HIGH|
|10|Modernize architecture : densify usage (ex AKS vs VMs) + auto scaling (VMSS, AKS, Serverless DB, …)|MEDIUM|HIGH|

## Azure Reservation 
### Why 
**Save Money** with Azure reservation.  
Learn how Azure Reservations help you save money by committing to one-year or three-years plans for virtual machines, Azure Blob storage or Azure Data Lake Storage Gen2, SQL Database compute capacity, Azure Cosmos DB throughput, and other Azure resources.  

The above lines are the exhibit of the official online documentation available [here](https://docs.microsoft.com/en-us/azure/cost-management-billing/reservations/)

### to know 
- All reservations, except Azure Databricks, are applied on an **hourly basis**
- Unused reserved capacity doesn't carry over from one hour to next, in other words unused reserved capacity is **lost**
- Usage exceeding the reserved quantity is charged using more expensive pay-as-you-go rates
- VM reservation is tied to a VM series  
> [!NOTE]
> Reservation purchased for ES series VMs don't apply to E series VMs, and vice-versa.
 

### How to 
Determine what to purchase with 
- Azure advisor virtual machines only 
- Reservation purchase experience in the Azure portal
- Cost Management Power BI app
- APIs

Azure advisor is the easiest way to identify **virtual machine** reserve instance to buy  
https://ms.portal.azure.com/#blade/Microsoft_Azure_Expert/AdvisorMenuBlade/Cost
![](media/cost-optimisation-checklist/RIAdvisor.png)

### Reconmmendations and best practices
- VM standardization should be pushed to simplify the azure VM reservation adoption. 
- VM shared scope should used to maximise utilisation, details of scope [here](https://docs.microsoft.com/en-us/azure/cost-management-billing/reservations/prepare-buy-reservation#scope-reservations)

### Pain points and difficulties
- Charge back to line of business  
In case the azure reservation are bought centrally and assigned to a shared scope subscription, charge back process could be very complex.   
VM Reservation Instance (RI) are assigned randomly to any suitable VM and can flip from one VM to another multiple times during a day.  
Distribution of discount can be them very complex if you want all the lines of business to benefit from the same.  
EG: if you have 3 identicals VMs in 3 subscriptions, and 2 Reservations VMs on day 1 it could be assigned to VM1 and VM3 and day 2 to VM1 and VM2, and day 3  
![](media/view-reservations/RI-chargeback-example.png)
