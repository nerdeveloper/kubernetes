# PodPresets

## Alpha status

As long as the PodPresets is in alpha status, the following changes need to be made in kops:

```bash
spec:
  kubeAPIServer:
    enableAdmissionPlugins:
    - Initializers
    - NamespaceLifecycle
    - LimitRanger
    - ServiceAccount
    - PersistentVolumeLabel
    - DefaultStorageClass
    - DefaultTolerationSeconds
    - MutatingAdmissionWebhook
    - ValidatingAdmissionWebhook
    - NodeRestriction
    - ResourceQuota
    - PodPreset
    runtimeConfig:
      settings.k8s.io/v1alpha1: "true"

```

## running the demo

First apply the PodPresets:

```bash
kubectl create -f pod-presets.yaml
```

Then run the deployments

```bash
kubectl create -f deployments.yaml
```
