# Intro to Kubernetes Cheat Sheet

## minikube

The host for our cluster. Good for development and experimentation

- `minikube start`
- `minikube stop`
- `minikube delete`

## kubectl

The primary tool for interacting with our cluster.

### create

- `kubectl create <resource>` Create a resource. 
	- `kubectl create deployment --image=<path to image>`
- `kubectrl create deployment -o yaml --dry-run=client ...`
	- Create the YAML for a deployment, do not actually run it

### expose

- `kubectl expose deployment <deployment name> --type=<type> --port=<port>`
	- Expose a deployment to the wider internet 
	- type can be ClusterIP, NodePort, LoadBalancer, ExternalName
	- NodePort exposes a specific port on each Node
	- LoadBalancer creates external load balancer which provides a fixed IP for the service	

### get

Get information about a resource or resources

- `kubectl get pods` All pods in the default namespace
- `kubectl get pods -A` All pods across namespaces
- `kubectl get service` Services
- `kubectl get deployment <name> -o yaml` Retrieve the YAML for this deployment

### describe

- `kubectl describe <resource> <identifier>` Give details about the given resource
- `kubcectl describe pod <podname>` will provide useful information about `podname`
- `kubectl describe pods` describes all pods

### scale

### label

### explain

### General commands

- `kubectl api-resources` list all resource types in Kubernetes
- `kubectl logs <resource>` Get the logs for a given pod (by name) or resource
	- Resource is often a pod, but can be another resource as well 
- `kubectl proxy --port=<port>` (Run in a separate terminal) establishes a connection between the Kubernetes API and the host
	-- Assumes port 8001 if you leave it off