# STARTX kustomize : demo-deployment

This kustomize is used to configure cluster generic behaviours like image prunning and cluster auto-scaling capacity

## Requirements and guidelines

Read the [startx kustomize-repository homepage](https://startxfr.github.io/kustomize-repository) for
more information on how to use theses resources.

## Deploy this kustomize on openshift

```bash
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-deployment
```

## use kustomize to build content

```bash
kustomize build github.com/startxfr/kustomize-repository/kustomizes/demo-deployment
```

## Base profile

Simple deployment of an Apache webserver (based on `quay.io/startx/apache:latest` image) running as a deamon container.

## Overlays profiles

- **default** : base configuration.
- **alpine** : base configuration, but running with `quay.io/startx/apache:alpine3` image
- **centos7** : base configuration, but running with `quay.io/startx/apache:centos7` image
- **centos8** : base configuration, but running with `quay.io/startx/apache:centos8` image
- **fc30** : base configuration, but running with `quay.io/startx/apache:fc30` image
- **fc31** : base configuration, but running with `quay.io/startx/apache:fc31` image
- **fc32** : base configuration, but running with `quay.io/startx/apache:fc32` image
- **ubi** : base configuration, but running with `quay.io/startx/apache:ubi8` image

## Overlays examples

```bash
# base configuration running quay.io/startx/apache:latest
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-deployment/base
# default configuration (iso base config)
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-deployment/overlays/default
# base configuration running with alpine 3 image flavour
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-deployment/overlays/alpine
# base configuration running with centos 7 image flavour
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-deployment/overlays/centos7
# base configuration running with centos 8 image flavour
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-deployment/overlays/centos8
# base configuration running with Fedora 30 image flavour
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-deployment/overlays/fc30
# base configuration running with Fedora 31 image flavour
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-deployment/overlays/fc31
# base configuration running with Fedora 32 image flavour
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-deployment/overlays/fc32
# base configuration running with UBI 8 image flavour
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-deployment/overlays/ubi
```

## History

| Release | Date       | Description
| ------- | ---------- | -----------------------
| 0.0.1   | 2020-10-04 | Initial commit
| 0.0.2   | 2020-10-10 | Move to suffix based naming
| 0.0.3   | 2020-10-10 | Add fedora,centos,ubi and alpine overlays
| 0.0.4   | 2020-10-10 | Remove patch and add label for generator
| 0.0.5   | 2020-10-10 | Improve started command
| 0.0.11  | 2020-11-21 | Start moving documentation to readthedocs
| 0.1.19  | 2020-11-23 | Official documentation moved kustomize-repository.readthedocs.io and improve complete repository release lifecycle
| 0.1.20  | 2020-11-23 | Stable version with documentation and example values for all packages
