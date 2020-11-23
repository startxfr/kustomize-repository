# STARTX kustomize repository

[![startx kustomize repository](https://img.shields.io/badge/latest-v0.1.20-blue.svg)](https://github.com/startxfr/kustomize-repository)

Repository of kustomize ressources for various infrastructure configuration and services running under an Openshift Container Platform (or OKD).
For more informations and access to the kustomize index, you can visit the [startx kustomize-repository homepage](https://startxfr.github.io/kustomize-repository).

## Kustomize repository content

This repository host various kustomize targeting the Openshift Container Platform environment. Hereby is a list of kustomize packages availables in this repository, and sample to deploy it under your current openshift cluster (must be logged with appropriate rights).

| Kustomize                                  | Source                                                                                            | Description  
| ------------------------------------------ | ------------------------------------------------------------------------------------------------- | -------------------------------------
| **[example](packages/example.md)**         | [source](https://github.com/startxfr/kustomize-repository/tree/master/kustomizes/example)         | deploy a simple nginx pod exposed via a service
| **[example](packages/demo-pod.md)**        | [source](https://github.com/startxfr/kustomize-repository/tree/master/kustomizes/demo-pod)        | deploy a static pod
| **[example](packages/demo-deployment.md)** | [source](https://github.com/startxfr/kustomize-repository/tree/master/kustomizes/demo-deployment) | deploy a pod supervised by a deployment
| **[example](packages/demo-sxapi.md)**      | [source](https://github.com/startxfr/kustomize-repository/tree/master/kustomizes/demo-sxapi)      | deploy a small api motorized by sxapi and supervised by a deployment

## Examples

```bash
# using example package with various profiles
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/example
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/example/base
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/example/overlays/default
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/example/overlays/single
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/example/overlays/heavy
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/example/overlays/dev
# using all available packages with default profile
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/example
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-pod
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-deployment
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-sxapi
```

## Install this repository

### 1. Requirements

#### 1.1. install cli dependencies

```bash
yum install yq -y
```

#### 1.2. install kustomize executable

```bash
yum install kustomize -y
```

#### 1.3. Connect to an openshift cluster

```bash
oc login -t <my-token> <my-openshift-api>
```

If you don't have access to an openshift cluster, consider using codeready-container to
run locally a simulated cluster.

### 2. Install repository

#### 2.1. Install this repository

```bash
git clone https://startxfr.github.io/kustomize-repository.git
cd kustomize-repository
```

#### 2.2. List all kustomize packages

```bash
ls kustomizes
```

### 3. Install a kustomize

```bash
# oc apply -k kustomizes/<package>
# oc apply -k kustomizes/<package>/<profile>
oc apply -k kustomizes/demo-pod
oc apply -k kustomizes/demo-deployment
oc apply -k kustomizes/demo-deployment/apache
oc apply -k kustomizes/demo-deployment/mysql
oc apply -k kustomizes/demo-sxapi
```

## Install building environment

In order to get the full developement environment, you must follow the [install build environment guide](install-build)

## History and releases

Latest release of this repository is v0.0.11 released at 2020-11-21 10:00:00. Read history [traceback](history) for more information
on change and released version. Complementary information could be found in the [release convention](releases)
