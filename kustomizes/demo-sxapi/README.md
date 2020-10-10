# STARTX kustomize : demo-sxapi

This kustomize is used to configure cluster generic behaviours like image prunning and cluster auto-scaling capacity

## Requirements and guidelines

Read the [startx kustomize-repository homepage](https://startxfr.github.io/kustomize-repository) for
more information on how to use theses resources.

## Deploy this kustomize on openshift

```bash
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-sxapi
```

## use kustomize to build content

```bash
kustomize build github.com/startxfr/kustomize-repository/kustomizes/demo-sxapi
```

## Base profile

Simple deployment of an web-exposed API based on sxapi framework (based on `startx/sxapi:latest` image).
You also have a kustomize for project creation under `ns/` directory (see examples).

## Overlays profiles

- **default** : base configuration.
- **testing** : base on default overlays, but running with `startx/sxapi:testing` image
- **0.3** : alias to 0.3.53 overlays
- **0.3.52** : base configuration, but running with `startx/sxapi:0.3.52` image
- **0.3.53** : base configuration, but running with `startx/sxapi:0.3.53` image
- **0.2** : alias to 0.2.99 overlays
- **0.2.99** : base configuration, but running with `startx/sxapi:0.2.99` image

## Overlays examples

```bash
# Create the namespace for testing this collection of kustomize overlays
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-sxapi/ns
# base configuration running startx/sxapi:latest
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-sxapi/base
# default configuration (iso base config)
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-sxapi/overlays/default
# base configuration running with alpine 3 image flavour
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-sxapi/overlays/testing
# alias to 0.3.53 overlays
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-sxapi/overlays/0.3
# base configuration running with sxapi version 0.3.52 image
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-sxapi/overlays/0.3.52
# base configuration running with sxapi version 0.3.53 image
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-sxapi/overlays/0.3.53
# alias to 0.2.99 overlays
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-sxapi/overlays/0.2
# base configuration running with sxapi version 0.2.99 image
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/demo-sxapi/overlays/0.2.99
```

## History

| Release | Date       | Description
| ------- | ---------- | -----------------------
| 0.0.1   | 2020-10-10 | Initial commit
| 0.0.2   | 2020-10-10 | Remove patch and clean deployment
| 0.0.3   | 2020-10-10 | Add various sxapi flavour examples
| 0.0.4   | 2020-10-10 | Add support for ns and stable releases
