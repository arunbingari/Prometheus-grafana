# Deploying Prometheus and Grafana using Helm in EKS
This project aims to demonstrate how to deploy Prometheus and Grafana using Helm in an EKS (Elastic Kubernetes Service) cluster.

To learn more about the process, check out my blog post on this topic.

## Prerequisites
Before you begin, you will need the following:

1. An AWS account
2. An EKS cluster
3. A running Kubernetes cluster
4. Helm installed on your system

## Installation

### Step 1:
 Install Helm by following the instructions provided in the official Helm documentation.
### Step 2:
 Add the Prometheus and Grafana repositories to Helm using the following commands:

    ```
     helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
     helm repo add grafana https://grafana.github.io/helm-charts

    ```
### Step 3:
 Install Prometheus using the following command:

    ```
     helm install prometheus prometheus-community/kube-prometheus-stack
    ```
### Step 4:
 Install Grafana using the following command:
    ```
    helm install grafana grafana/grafana
    ```
### Step 5:
 Access Grafana by exposing the Grafana service using the following command:
    ```
    kubectl port-forward svc/grafana 3000:80
    ```
## Conclusion

With Prometheus and Grafana deployed using Helm in an EKS cluster, you can monitor your Kubernetes cluster and applications easily and efficiently. This project provides a simple and straightforward way to get started with monitoring your Kubernetes resources.