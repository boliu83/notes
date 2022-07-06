---
description: Create new ARO cluster from CLI
---

# CLI

1. Get pull secret from Redhat [https://cloud.redhat.com/openshift/install/pull-secret](https://cloud.redhat.com/openshift/install/pull-secret) (account registration required)\

2. Determine following parameters for your cluster
   * Location
   * Resource Group Name
   * Openshift Cluster Name
   * &#x20;VNet and subnets name\
     2 subnets are required for masters and workers\

3. Create your cluster

```
export LOCATION=<location>
export GROUP=<resource_group>
export CLUSTER=<cluster>
export VNET=<vnet>


az group create --name $GROUP -l australiaeast

az network vnet create --resource-group $GROUP \
 --name $VNET --address-prefixes 192.168.0.0/22

az network vnet subnet create -g $GROUP --vnet-name $VNET --name master-subnet\
 --address-prefixes 192.168.0.0/23 --service-endpoints Microsoft.ContainerRegistry

az network vnet subnet create -g $GROUP --vnet-name $VNET --name worker-subnet\
 --address-prefixes 192.168.2.0/23 --service-endpoints Microsoft.ContainerRegistry

az network vnet subnet update --name master-subnet --resource-group $GROUP\
 --vnet-name $VNET --disable-private-link-service-network-policies true

az aro create -g $GROUP --name $CLUSTER --vnet $VNET --master-subnet master-subnet \
 --worker-subnet worker-subnet --pull-secret @secret.txt
```
