# Introduction

## Module info

* **Duration:** ~5 hours 
* **Works with k8s version** 1.24
* **Workshop Domain:** *.workshop.metakube.org
* **Optimized for** Linux and MacOS
* Windows Users use WSL and/or PowerShell

## Prerequisites

You need to have these tools installed on your local machine:

- kubectl (>1.24)
- helm (>3.10)
- linkerd (>2.12.4)

Further this workshop is based on SysEleven's "Production Grade Deployment" workshop and we
assume you have these services up and running:

- Ingress Controller: ingress-nginx
- cert-manager
- external-dns

## Preparation

* Before you begin with the actual exercise please make sure to follow these steps to work in your own environment:

  ```shell
  read -p "Please enter your name (without blanks e.g. johndoe): " YOURNAME
  export YOURNAME
  kubectl create ns ${YOURNAME}
  kubectl label namespace ${YOURNAME} deepdive-observability=true
  kubectl config set-context --current --namespace=${YOURNAME}
  ```

* Clone this repository to your working station and change into the directory for the following exercises

## Start with

Exercise [101-kube-prometheus-stack](../101-kube-prometheus-stack/README.md)

## Landscape

You will share a single Kubernetes cluster with other workshop participants.
Your own examples can be executed and tested in you personal namespace.
