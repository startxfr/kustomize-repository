# kustomize-repository

Repository of kustomize ressources to deploy infrastructure components

# kustomize-repository

Repository of kustomize ressources for various infrastructure configuration and services running under an Openshift Container Platform (or OKD).
For more informations and access to the kustomize index, you can visit the [repository homepage](https://startxfr.github.io/kustomize-repository/).

## Install component from repository

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

### 3. Install a kustomize

```bash
cd kustomizes
oc apply -k cluster-config/dev
```

## Install building environment

In order to get the full developement environment, you must stick to the following procedure

### 1. Get a copy of the repository

```bash
git clone https://github.com/startxfr/kustomize-repository.git
cd kustomize-repository
```

### 2. Create a new kustomize

```bash
./sx-kustomize mykustomize create
```

### 3. Test a kustomize

```bash
./sx-kustomize mykustomize test
```

### 4. Package a kustomize

```bash
./sx-kustomize mykustomize package
```

### 5. Release a kustomize

```bash
./sx-kustomize mykustomize package auto
```

### 6. Delete a kustomize

```bash
./sx-kustomize mykustomize delete
```

## Release convention

- MAJOR version for major kustomize structural changes that lead to break the compatibility with previous version (ex: X.0.0)
- MINOR version for major functionality ehancement added in a backwards compatible manner (ex: 0.X.0)
- PATCH version for bug, security and functionnals updates, backwards compatible for continous delivery (ex: 0.0.X)
- PRE-RELEASE version for an unstable release that might not satisfy the intended compatibility requirements (ex: 0.0.0-beta)
- BUILD version to identify to differents build during release preparation (ex: 0.0.0-tag)

Only MAJOR, MINOR and PATCH are mandatory for releasing an application.

Minor or patch release with an **odd number** are used for **stable** and releasable version.
A **even** minor or patch number indicate a release **not stable** and releasable.

The CI chain will run integration test suite and promote to a stable release number the code if
test are OK.

### Examples

- major release : `0.1.17` to `1.0.0`
- minor release : `1.0.0` to `1.1.0`
- patch release : `1.1.0` to `1.1.1`
- pre-release : `1.1.1` to `1.1.2-alpha`
- build release : `1.1.2+20200313144700` or `1.1.2-alpha+20200313144700`

## Release rules

- Major releases defined by startx strategy (driven by technology improvments)
- Minor releases defined by cross-kustomize, startx's driven roadmap
- Patch releases defined by technical issues related to kustomizes
- pre-release defined as part of major and minor release lifecycle
- build release used only during dev, test, build CI operations

## Release history

### version 0.0.x (chanteix)

| Release | Date     | Description                                     |
| ------- | -------- | ----------------------------------------------- |
| 0.0.1   | 20-10-04 | Initial commit                                  |
