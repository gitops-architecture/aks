# Create an Azure Kubernetes Service (AKS) Cluster using Tekton

There are many ways in which you can provision an AKS cluster. For instance, you can use Azure Cli, or use powershell script along with Azure Resource Manager (ARM) Templates, or use a configuration tool such as Terraform, to name a few. In this repo, we will demonstrate how to use Tekton Pipelines object, a Task and a Taskrun to create an AKS cluster named as _gitops-aks_ in a Azure resource group called _gitops-ask_rg_. 

**Prerequisites**  
This repo assumes you have installed [Tekton Pipelines (v0.9.2)](https://github.com/tektoncd/pipeline) and optionally, [Tekton Dashboard (v0.3.0)](https://github.com/tektoncd/dashboard) in an existing Kubernetes cluster, either another AKS cluster or a local k8s cluster such as _Minikube_, _Kind_ or _Docker-Desktop_ with k8s enabled).

To create a AKS cluster, follow the steps below:
1. Clone [this repo](https://github.com/gitops-architecture/aks).
2. Edit task.yaml, replacing the following with appropriate values:
    - YOUR_AZURE_APPI
    - YOUR_AZURE_PASSWORD
    - YOUR_AZURE_TENANTID
    - YOUR_AZURE_SUBSCRIPTION
3. Run the following command in the a shell:
```
$ kubectl apply -f task.yaml
$ kubectl create -f taskrun.yam
```
Depending on the time of the day or where you are, it may take about 15 minutes for the AKS cluster to be created and ready.

The following screenshot shows the AKS cluster _gitops-aks_ in the resource group _gitops-aks_rg_:  

![AKS cluster](./images/AKS-cluster.JPG)