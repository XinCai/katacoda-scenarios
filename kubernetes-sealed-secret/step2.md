# Installing the custom controller and CRD for SealedSecret

### Second part:
2. Install A cluster-side controller / operator

The latest release at the time of writing this post was v0.15.0 and can be installed on a Kubernetes cluster in a single step using kubectl as shown by the following command.
 
### install the controller

```
kubectl apply -f https://github.com/bitnami-labs/sealed-secrets/releases/download/v0.15.0/controller.yaml
```

### verify the controller installation

```
kubectl get pods -n kube-system | grep -i sealed-secrets-controller
```
