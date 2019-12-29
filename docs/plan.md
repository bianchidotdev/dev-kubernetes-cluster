# Plan

## Components

1. Kubernetes cluster hosted on GKE
2. Global (non-namespaced) Ingress controller handling all services (likely [Traefik](https://docs.traefik.io/))
3. Let's Encrypt managed SSL certificates (should be handled by ingress controller)
4. GCP managed load balancer (either with static IPs or auto-updating DNS records)
5. RBAC for each developer with limited access by namespace and resource utilization
6. Terraformed (or other) setup of the cluster itself
7. CI and CD for deployment of cluster and applications (likely github actions and/or spinnaker)
