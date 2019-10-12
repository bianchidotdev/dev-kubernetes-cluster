# Kubernetes Research

## Simple

### Core Concepts

* Cluster
  * 
* Deployment
* Service - Provides an abstract wrapper around a set of pods - used to allow for a single endpoint which keeps  track of all the IPs of the pods serving a particular app \(uses match labels\)
* Pod
* Container

### Additional Concepts

* VirtualService - allows you to match routes to upstream clusters by attaching them to a gateway. This idea can be likened to using Kubernetes Ingress along with an Ingress Controller
* Gateway - Declares which endpoints to serve

### Resources

* k8s on a budget - [https://www.doxsey.net/blog/kubernetes--the-surprisingly-affordable-platform-for-personal-projects](https://www.doxsey.net/blog/kubernetes--the-surprisingly-affordable-platform-for-personal-projects)
* 
## Istio

Service mesh configuration engine that manages L7 Network traffic with the Envoy Proxy.

Manages all network requests and directs all ingress and egress through the Envoy Proxy

### Core Concepts

* Envoy Proxy - Data plane for proxying - gRPC based proxy managed by Pilot
* Pilot - Control plane for proxying - tells source and destination envoy proxies how to communicate and provides all the traffic rules Envoy needs to discover and route traffic within the cluster
* Sidecar Injector - Modifies PodSpec for all newly created Pods to include 2 additional containers, one for setting up proxy rules and the second for proxying
* Istio Cluster - Manages K8s Endpoints - maps conceptually to a K8s Service
* Istio Listener - Maps conceptually to a K8s Endpoint
* Istio Route - Replacement for the traditional K8s Ingress, using a VirtualService instead

When Pods, Services, or Endpoints are updated or created in Kubernetes, those changes are sent to Pilot, which will then send the proper configuration down to every connected Envoy instance.

### Resources

* [https://medium.com/namely-labs/a-crash-course-for-running-istio-1c6125930715](https://medium.com/namely-labs/a-crash-course-for-running-istio-1c6125930715)

## To Research

* External DNS with managed certificates
* Internal DNS with managed certificates
* 
