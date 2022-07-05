# Argo Rollouts base module

This directory is to serve as a base for kustomization of Argo Rollouts.

The reason a separate directory is necessary is because there is no simple way to exclude base configuration with kustomize, without creating large amounts of yaml code.

With this, all environments which require Argo Rollouts, as opposed to vanilla Kubernetes Deployments, may add this directory in the appropriate kustomization.yaml file for said environments.
