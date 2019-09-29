# Kubernetes setup

Access the test app at http://dev.blualism.com

## Details

This is a simple Kubernetes cluster set up with a single app pod running a test webserver, running nginx as a DaemonSet to avoid paying for expensive managed LoadBalancer services.

The most complex part of this is setting up DNS to update everytime a new node is provisioned.

## TODO
Implement [external-dns](https://github.com/kubernetes-incubator/external-dns) instead of less flexible cloudflare-dns-sync

Manage cluster setup and secret creation using terraform

Research how to handle GCP user access

Set up managed certificates with Let's Encrypt

Set up kustomize for managing several environments within the same cluster (namespaced off)

Optionally, set up Istio as a service mesh
