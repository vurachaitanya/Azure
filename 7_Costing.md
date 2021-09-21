### 3 types of cost estimation
- Cost calculator
- Cost estimation from portal
- Azure Advisor services to optimizes the costing

##### Cost calculator: [Link](https://azure.microsoft.com/en-us/pricing/calculator)
- Calculate for different resources 
- Give name for resources like vm for prod, vm for dev etc.
- Converts the currency based location.
- Can save and export the cost estimation.

##### Cost Estimation from portal :
- Dashboard --> Subscription --> Overview
- Will give detailed cost.
- Cost based on current and forecast
- Dashboard --> Subscription --> Cost Management --> Cost analysis
- **Cost Analysis :** to get better cost analysis, apply filters, excel formulas like group by resources, time period, Tags etc.


##### Advisor 
- Dashboard --> Subscription --> Advisor
- Dashboard --> Advisor recommendation
- Created across 4 pillers 
  - High Availability
  - Security
  - Performance
  - Cost 
    - Optimize VM spend by resizing or shutting down underutilized instances.
    - Reduce cost by unprovisioned ExpressRoute cricuits
    - Buy reserved VM instances to save money, when compared to Pay as you go costing.
    -  Reduce costs by deleting or reconfiguring idle VNet Gateways.

![Dashboard](https://docs.microsoft.com/en-us/azure/advisor/media/advisor-overview/advisor-dashboard.png)
