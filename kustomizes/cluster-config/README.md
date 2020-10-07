# STARTX kustomize : cluster-config

This kustomize is used to configure cluster generic behaviours like image prunning and cluster auto-scaling capacity

## Deploy this kustomize on openshift

```bash
oc apply -k github.com/startxfr/kustomize-repository/kustomizes/cluster-config
```

## use kustomize to build content

```bash
kustomize build github.com/startxfr/kustomize-repository/kustomizes/cluster-config
```

## More informations

Read the [startx kustomize-repository homepage](https://startxfr.github.io/kustomize-repository) for
more information on how to use theses resources.
