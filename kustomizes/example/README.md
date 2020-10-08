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

## Overlays profiles

- **default** : Complete example of a kustomize file with image update, configmap generator, merge and json6902 patches.
- **single** : Deployment reduced to one replica
- **heavy** : Deployment augmented to 3 replica
- **dev** : Deployment of nginx 1.9.2

## History

| Release | Date       | Description
| ------- | ---------- | -----------------------
| 0.0.1   | 20-10-04   | Initial commit
| 0.0.2   | 2020-10-08 | Add heavy,single and dev overlays
