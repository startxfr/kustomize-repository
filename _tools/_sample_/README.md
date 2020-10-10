# STARTX kustomize : _sample_

This kustomize is used to configure cluster generic behaviours like image prunning and cluster auto-scaling capacity

## Requirements and guidelines

Read the [startx kustomize-repository homepage](https://startxfr.github.io/kustomize-repository) for
more information on how to use theses resources.

## Deploy this kustomize on openshift

```bash
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/_sample_
```

## use kustomize to build content

```bash
kustomize build github.com/startxfr/kustomize-repository/kustomizes/_sample_
```

## Base profile

Simple deployement of linux image (based on `quay.io/startx/fedora:latest` image)

## Overlays profiles

- **default** : base configuration.
- **xxxxx** : base configuration, but with xxxx change

## Overlays examples

```bash
# base configuration
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/_sample_/base
# default configuration (iso to base config)
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/_sample_/overlays/default
# xxxxx configuration with yyyyyy changes
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/_sample_/overlays/xxxxx
```

## History

| Release | Date       | Description
| ------- | ---------- | -----------------------
| 0.0.1   | 20-10-04   | Initial commit
