# Red Hat OpenShift single zone cluster on IBM Cloud
Copyright IBM Corp. 2020 

This code is released under the Apache 2.0 License.

## Overview
This terraform template deploys a Red Hat OpenShift cluster in single zone on IBM Cloud.

Via this template, a configurable number of worker nodes can be deployed.

## Prerequisites
The user must be assigned the following access policies to deploy and manage clusters within ROKS
  * The Administrator IBM Cloud IAM platform role for IBM Cloud Kubernetes Service
  * The Administrator IBM Cloud IAM platform role for IBM Cloud Container Registry
  * The Writer or Manager IBM Cloud IAM service role for IBM Cloud Kubernetes Service

## Template input parameters

| Parameter name         | Parameter description |
| :---                   | :---        |
| region                 | IBM Cloud region in which to deploy the cluster |
| cluster_name           | Name of the ROKS cluster. Cluster name can have lower case alphabets, numbers and dash. Must start with lower case alphabet and end with alpha-numeric character. Maximum length is 32 characters. |
| resource\_group\_name  | Name of the IBM Cloud resource group. You must have access to at least one resource group in IBM Cloud |
| private\_vlan\_id      | Virtual network that allows private communication between worker nodes in this cluster. Can be retrieved by running bx cs vlans <location> |
| public\_vlan\_id       | Virtual network that allows secured communication between the worker nodes and the IBM-managed master node. Can be retrieved by running bx cs vlans <location> |
| subnet_id              | The portable subnet to use for cluster. A list of available subnets can be retrieved by running bx cs subnets |
| num_workers            | Number of workers to be deployed in the cluster. |
| datacenter             | IBM Cloud datacenter in which to create the cluster. |
| machine_type           | Machine type for the worker node(s). |
| isolation              | Hardware isolation ('shared', 'dedicated' or 'baremetal'). |
| roks_version           | Red Hat OpenShift version for the cluster.  |

## Template output
| Parameter name         | Parameter description |
| :---                   | :---        |
| cluster_name           | Cluster name. |
| cluster_config         | Base64 encoded content of the kubeconfig yaml file. |

