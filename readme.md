# Microsoft Azure compute decision tree

Let's start with a disclaimer: Microsoft Azure services rapidly evolve so keep in mind that the information shared in this article can become outdated over time. 
The number of compute options where you can run your application in Azure increased significantly over the last couple of years and the number of options can be overwhelming for a lot of people or organizations that are new to Azure.
In my many conversations with different organizations I often get the question if there is some guidance on when to use which compute option that can guide their internal DevOps teams. 
On the public Azure documentation website we provide a decision tree 	[Choosing an Azure compute service](https://docs.microsoft.com/en-us/azure/architecture/guide/technology-choices/compute-decision-tree) but this doesn’t include all compute options and it’s very high level. Based on my conversations I tried to build a decision tree that provides a little more guidance. 

This decision tree only includes **Azure first party services**. A first party Azure service is a service that is delivered and managed by Microsoft. A first party service can be based on third-party technology which Microsoft delivers as an Azure native service. Organizations can also leverage third-party services that can be deployed onto Microsoft Infrastructure Services. These are not included in this decision tree.
Please find the compute decision tree below

![Picture of decision tree](/images/AzureComputeDecisionTree.png)

Important to understand is that the questions that influence a decision can be arbitrary or seen as an opinionated view. It’s intended this way. There are always nuances in the choices because most decisions are multi-dimensional and it’s always a challenge to get a multiple dimension into 2-dimensional decision tree. 
Special note on Azure Functions and Azure Container instances (CI). Both services provide a serverless option to run your code but aren’t commonly used to run an entire application. These services are mostly used as part of larger event-based application architecture in which they’re handling a specific task triggered by an event. CI can also be used for more specific use cases like elastic bursting with AKS [link](https://docs.microsoft.com/en-us/azure/architecture/solution-ideas/articles/scale-using-aks-with-aci) or within the development process where you want quickly test if the container works or in your build process where you need a container to do certain tasks.

## What about High Performance Computing (HPC)?

I left the high performance computing options out because these are mostly used by very specialized applications and required special attention. If you want to know more about the HPC options here are the references to the different options:
•	**Azure HPC (H) series Virtual Machines** [link](https://docs.microsoft.com/en-us/azure/virtual-machines/sizes-hpc): specialized infrastructure with optional high-throughput network interfaces (RDMA) to support almost any type of HPC workload. 
•	**Azure Batch** [link](https://docs.microsoft.com/en-us/azure/batch/batch-technical-overview)is a managed service for running large-scale parallel and high-performance computing applications.
•	**Azure CycleCloud** [link](https://docs.microsoft.com/en-us/azure/cyclecloud/overview?view=cyclecloud-8)is a service for creating, managing, operating, and optimizing HPC & Big Compute clusters in Azure. With Azure CycleCloud, users can dynamically provision HPC capable Virtual Machines with Infiniband interfaces and orchestrate data and jobs for hybrid and cloud workflows.

You can find the source of the [decision tree](https://github.com/MarcvanHouten/AzureComputeDecisionTree/blob/main/AzureComputeDecisionTree.drawio) in this repository. I used the free draw.io solution to create the decision tree so anyone can edit it and tailor it to their needs. If you’re looking for Azure icons, these can be downloaded via the [Azure Architecture Center](https://docs.microsoft.com/en-us/azure/architecture/icons/).

I hope this decision tree provides you some guidance. Please reach out if you miss things or have a different opinion on certain decisions.



