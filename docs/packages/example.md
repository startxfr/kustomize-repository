# STARTX kustomize : example

Complete example of a kustomize file with image update, configmap generator, merge and json6902 patches.

## Requirements and guidelines

Read the [startx kustomize-repository homepage](https://startxfr.github.io/kustomize-repository) for
more information on how to use theses resources.

## Deploy this kustomize on openshift

```bash
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/example
```

## use kustomize to build content

```bash
kustomize build github.com/startxfr/kustomize-repository/kustomizes/example
```

## Base profile

Simple deployement of nginx 1.7.9 with 2 replica and kustomize file using configMapGenerator, generatorOptions and var.

## Overlays profiles

- **default** : base with image update to nginx 1.9.1 and sample merge and json6902 patches.
- **single** : base with image update to nginx 1.9.0 and a deployment reduced to 1 replica
- **heavy** :  base with image update to nginx 1.9.0 and a deployment augmented to 3 replica
- **dev** : base with image update to nginx 1.9.2 and a deployment reduced to 1 replica

## Overlays examples

```bash
# base configuration (nginx 1.7.9 with 2 replica)
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/example/base
# default configuration (nginx 1.9.1 and patches on labels)
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/example/overlays/default
# default configuration with nginx 1.9.0 and 1 replica
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/example/overlays/single
# default configuration with nginx 1.9.0 and 3 replica
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/example/overlays/heavy
# default configuration with nginx 1.9.2 and 1 replica
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/example/overlays/dev
```

## History

| Release | Date       | Description
| ------- | ---------- | ---------------------------------
| 0.0.1   | 20-10-04   | Initial commit
| 0.0.2   | 2020-10-08 | Add heavy,single and dev overlays
| 0.0.3   | 2020-10-08 | Improve various configurations provided in heavy, single, dev, default overlays and base profile
| 0.0.4   | 2020-10-08 | Test for doc creation of this package
| 0.0.5   | 2020-10-10 | Move to suffix based naming
