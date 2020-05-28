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

### To know 
- List of azure workload covered by reservation is available [here](https://docs.microsoft.com/en-us/azure/cost-management-billing/reservations/save-compute-costs-reservations?toc=%2Fazure%2Fvirtual-machines%2Fwindows%2Ftoc.json#charges-covered-by-reservation). 
- All reservations, except Azure Databricks, are applied on an **hourly basis**.
- Azure reservation as a **scope**, scope definition [here](https://docs.microsoft.com/en-us/azure/cost-management-billing/reservations/prepare-buy-reservation#scope-reservations). 
- Reservation scope can be changed, details [here](https://docs.microsoft.com/en-us/azure/cost-management-billing/reservations/manage-reserved-vm-instance#change-the-reservation-scope).  
Example: previously assigned VM reservation to resource group can be changed to subscription for the reservation to be used across all the subscription. 
- Unused reserved capacity doesn't carry over from one hour to next, in other words unused reserved capacity is **lost**.
- Usage exceeding the reserved quantity is charged using more expensive pay-as-you-go rates.
- VM reservation is tied to a VM series.  
Reservation purchased for ES series VMs do not apply to E series VMs, and vice-versa.  
- VM reservation consumption is subject to ratio when size flexibility is enable, details [here](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/reserved-vm-instance-size-flexibility).  
**1 CPU VM reservation type is consumed 2 times quicker on a 2 CPUs VM from the same series.** 
- Software costs not included with Azure Reserved VM Instances, details [here](https://docs.microsoft.com/en-us/azure/cost-management-billing/reservations/reserved-instance-windows-software-costs).

### How to identify what to purchase.
Determine what to purchase with:
- Azure advisor virtual machines only 
- Reservation purchase experience in the Azure portal
- Cost Management Power BI app
- APIs

#### VM
Details can be found [here](https://docs.microsoft.com/en-us/azure/cost-management-billing/reservations/determine-reservation-purchase#reservation-purchase-recommendations).

Azure advisor is the easiest way to identify **virtual machine** reserve instance to buy  
https://ms.portal.azure.com/#blade/Microsoft_Azure_Expert/AdvisorMenuBlade/Cost
![](media/cost-optimisation-checklist/RIAdvisor.png)

### Monitor usage
It is critical to monitor reservation usage to avoid under-utilization and over spent.
how to view azure reservation usage can be found [here](https://docs.microsoft.com/en-us/azure/cost-management-billing/reservations/view-reservations).

### Reconmmendations and best practices
- VM standardization should be maximized to simplify azure VM reservation adoption. 
- VM shared scope should used to maximise utilisation, details of scope [here](https://docs.microsoft.com/en-us/azure/cost-management-billing/reservations/prepare-buy-reservation#scope-reservations)
- When azure reservation are bought centrally, businesses lines should be consulted before buying to get long term visibility and potential decomissionning, replatforming, migration to new application architecture, ...

### Pain points and difficulties
- **Charge back** to internal businesses lines.  
In case the azure reservation are bought centrally and assigned to a shared scope subscription, charge back process could be very complex.   
VM Reservation Instance (RI) are assigned randomly to any suitable VM and can flip from one VM to another multiple times during a day.  
Distribution of discount can be then very complex if you want all the lines of businesses to benefit equal discount.  
EG: if you have 3 identicals VMs in 3 subscriptions, and 2 Reservations VMs, on day 1 it could be assigned to VM1 and VM3 and day 2 to VM1 and VM2, and day 3 to again VM1 and VM2 
![](media/view-reservations/RI-chargeback-example.png)
    > [!NOTE]
    > - How to view amortized charge back in azure portal is explained [here](https://docs.microsoft.com/en-us/azure/cost-management-billing/reservations/charge-back-usage).  
    > - How to get it from the EA portal as a csv file [here](https://docs.microsoft.com/en-us/azure/cost-management-billing/reservations/understand-reserved-instance-usage-ea).  
    > - How to get it for an individual subscription as a csv file [here](https://docs.microsoft.com/en-us/azure/cost-management-billing/reservations/understand-reserved-instance-usage).
- **50K$ refund rolling limit**: you can refund reservation instance VM to a limit of 50K$ over a 1 year rolling period.  
- **refund and repurchase** new reservation: the new purchase total should equal or be greater than the returned amount
    > [!NOTE]
    > all the exchange and refund policies information can be found [here](https://docs.microsoft.com/en-us/azure/cost-management-billing/reservations/exchange-and-refund-azure-reservations#cancel-exchange-and-refund-policies). 