# Openshift manifests for LFY031/032 docker images

## `thoth-pytorch.yaml`

Base docker image based on 
[https://github.com/thoth-station/s2i-pytorch-notebook](https://github.com/thoth-station/s2i-pytorch-notebook)
Note: Base image no longer maintained since July 2022, should probably look for alternatives.

Add image to GU openshift cluster by applying this file, e.g.
```
oc apply thoth-pytorch.yaml
```

## `pytorch-jupyterhub-ext.yaml`

Extension of base image (`thoth-pytorch.yaml`) including RISE (presentation), testbook (automatic notebook testing), and onnxruntime.

Note: Assumes that the base image is already present in the cluster (see above).

Build image in cluster with
```
oc apply pytorch-jupyterhub-ext.yaml
```