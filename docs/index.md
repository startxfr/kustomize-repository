# This repository

This kustomize repository hold various kustomize configuring Openshift cluster components

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
