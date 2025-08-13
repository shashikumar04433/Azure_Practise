## Function App Tutorial:
```
* An Function App is basically the container / hosting environment in Azure.
  where one or more Azure Functions live and run.
```

**Types of Function App Plan**
```
* Consumption Plan
* Premium Plan
* Flex Consumption
* App Service Plan
* 
```
**Consumption Plan**
```
* Think of it as: Cheapest, simplest, “scale to zero” model.
* Pay only when functions run.
* cold start
* Automatic scaling based on triggers.
BEST FOR:
* Low-volume APIs, CRON jobs, queue processing.
* Small apps that don’t need VNET or custom compute.
```

**Consumption Plan's Disadvantage**
```
* No VNET integration.
* Cold starts.
* Fixed CPU/memory
```

**Premium Plan**
```
* Think of it as: Always-on, high-performance Function Apps.

Features:
* No cold start (instances always warm).
* Multiple function apps can run on the same plan.
* Event-driven automatic scaling.
* VNET integration.
* Longer execution times (up to 60 minutes).
```
**Flex Consumption**
```
Flex Consumption is the new generation of serverless hosting for Azure Functions.
It keeps the pay-as-you-go model from the classic Consumption plan but adds flexibility in compute sizing,
faster scaling, and networking capabilities like VNET integration.
```
**Flex Consumption Key Features**
```
* Pay-as-you-go – You only pay for execution time and resources used.
* Custom compute sizes – You can choose CPU and memory configurations (unlike the fixed 1.5 GB in classic Consumption).
* Virtual Network (VNET) integration – Access private resources securely without moving to Premium.
* Faster scaling – Handles burst workloads more efficiently.
* Scale-to-zero – No running costs when your function is idle.
* Max execution time up to 60 minutes – More flexible than classic Consumption (5–10 min).
```
