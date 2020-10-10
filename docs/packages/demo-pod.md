# STARTX kustomize : demo-pod

This kustomize is used to configure cluster generic behaviours like image prunning and cluster auto-scaling capacity

## Requirements and guidelines

Read the [startx kustomize-repository homepage](https://startxfr.github.io/kustomize-repository) for
more information on how to use theses resources.

## Deploy this kustomize on openshift

```bash
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-pod
```

## use kustomize to build content

```bash
kustomize build github.com/startxfr/kustomize-repository/kustomizes/demo-pod
```

## Base profile

Simple pod based on linux image (based on `quay.io/startx/fedora:latest` image) running as a deamon container.

## Overlays profiles

- **default** : base configuration.
- **alpine** : base configuration, but running with `quay.io/startx/alpine:3` image
- **centos7** : base configuration, but running with `quay.io/startx/centos:7` image
- **centos8** : base configuration, but running with `quay.io/startx/centos:8` image
- **fc30** : base configuration, but running with `quay.io/startx/fedora:30` image
- **fc31** : base configuration, but running with `quay.io/startx/fedora:31` image
- **fc32** : base configuration, but running with `quay.io/startx/fedora:32` image
- **ubi** : base configuration, but running with `quay.io/startx/ubi:8` image

## Overlays examples

```bash
# base configuration
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-pod/base
# default configuration (iso base config)
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-pod/overlays/default
# base configuration running with alpine 3 image
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-pod/overlays/alpine
# base configuration running with centos 7 image
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-pod/overlays/centos7
# base configuration running with centos 8 image
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-pod/overlays/centos8
# base configuration running with Fedora 30 image
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-pod/overlays/fc30
# base configuration running with Fedora 31 image
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-pod/overlays/fc31
# base configuration running with Fedora 32 image
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-pod/overlays/fc32
# base configuration running with UBI 8 image
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-pod/overlays/ubi
```

## History

| Release | Date       | Description
| ------- | ---------- | -----------------------
| 0.0.1   | 2020-10-04 | Initial commit
| 0.0.2   | 2020-10-10 | Add fedora,centos,ubi and alpine overlays
| 0.0.3   | 2020-10-10 | Improve documentation
| 0.0.4   | 2020-10-10 | Update doc releases
| 0.0.5   | 2020-10-10 | Improve started command
