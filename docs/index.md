# Purpose of this repository

Repository of kustomize ressources for various infrastructure configuration and services running under an Openshift Container Platform (or OKD).
For more informations and access to the kustomize index, you can visit the [repository homepage](https://startxfr.github.io/kustomize-repository).

## Kustomize list

List of kustomize packages availables in this repository, and sample to deploy it under your current openshift cluster (must be logged with appropriate rights).

- [cluster-config](packages/cluster-config.md)
  ```oc apply -k github.com/startxfr/kustomize-repository/kustomizes/cluster-config```
- [cluster-rbac](packages/cluster-rbac.md)
  ```oc apply -k github.com/startxfr/kustomize-repository/kustomizes/cluster-rbac```
- [demo-pod](packages/demo-pod.md)
  ```oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-pod```
- [demo-deployment](packages/demo-deployment.md)
  ```oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-deployment```
- [demo-sxapi](packages/demo-sxapi.md)
  ```oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-sxapi```
- [example](packages/example.md)
  ```oc apply -k github.com/startxfr/kustomize-repository/kustomizes/example```

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

Latest release of this repository is v0.0.1 released at 2020-10-13 10:00:00. Read history [traceback](history) for more information
on change and released version. Complementary information could be found in the [release convention](releases)











## Usage

### 1. Requirements

#### 1.1. install cli dependencies

```bash
yum install yq -y
```

#### 1.2. install kustomize

```bash
yum install kustomize -y
```

#### 1.3. Beiing connected to an openshift cluster

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

#### 2.2. List all kustomize in this repository

```bash
ls kustomizes
```

### 3. Install kustomize

```bash
cd kustomizes
oc apply -k cluster-config/default
```

## Kustomize list

- [cluster-config](https://github.com/startxfr/kustomize-repository/tree/master/kustomizes/cluster-config)
- [cluster-rbac](https://github.com/startxfr/kustomize-repository/tree/master/kustomizes/cluster-rbac)

## Release

Release naming and convention is described in the [release documentation](./releases.md).

### History

You can get a detailed list of this kustomize releases in the [history documentation](./history.md).
The current release is for theses kustomizes is 0.0.5. More information are available in [version 0.0 releases history](./history.md#version-00x-chanteix).
