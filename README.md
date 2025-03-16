# knative-trigger-tekton
Triggering Tekton Pipelines as a result of changes of Virtual Machine resources and delivered through the use of Knative Eventing

## Overview

The contents of this repository demonstrates how to use a Knative [ApiServerSource](https://knative.dev/docs/eventing/sources/apiserversource/) to trigger Tekton Pipelines when changes of OpenShift Virtual Machines (kubevirt) events are received.

An overview of the architecture can be found below:

<add diagram here>

## Prerequisites

The following prerequisites must be satisfied prior to deploying the solution contained within this repository

1. OpenShift Cluster
2. Access to an OpenShift Cluster with `cluster-admin` privileges
3. Installation of OpenShift Pipelines (Tekton)
4. Installation of OpenShift Serverless (Knative)
5. Installation of Knative Eventing
6. Installaton of OpenShift Virtulization (kubevirt)
7. OpenShift  Command Line Interfaces (cli) 

## Installation

1. Create a new namespace 

```shell
oc apply -f namespaces/apiserversource-example.yaml
```

2. Apply OpenShift Pipelines (Tekton_ resources

```shell
oc apply -f pipelines
```

3. Apply Knative resources

```shell
oc apply -f knative
```

## Validation
Verify the integration by deploying a (kubevirt) Virtual Machine  to trigger the Tekton pipeline
