# Welcome to STARTX kustomize repository

## Kustomize list

List of kustomize packages availables in this repository, and sample to deploy it under your current openshift cluster (must be logged with appropriate rights).

- [example](packages/example.md) ***([source](https://github.com/startxfr/kustomize-repository/tree/master/kustomizes/example))***
- [demo-pod](packages/demo-pod.md) ***([source](https://github.com/startxfr/kustomize-repository/tree/master/kustomizes/demo-pod))***
- [demo-deployment](packages/demo-deployment.md) ***([source](https://github.com/startxfr/kustomize-repository/tree/master/kustomizes/demo-deployment))***
- [demo-sxapi](packages/demo-sxapi.md) ***([source](https://github.com/startxfr/kustomize-repository/tree/master/kustomizes/demo-sxapi))***

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
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-pod
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-deployment
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-sxapi
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/example
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
```

## Install building environment

In order to get the full developement environment, you must follow the [install build environment guide](install-build)

## History and releases

Latest release of this repository is v0.0.11 released at 2020-11-21 10:00:00. Read history [traceback](history) for more information
on change and released version. Complementary information could be found in the [release convention](releases)
