# Sealing Kubernetes Secret

## create a Kubernetes secret 
```
kubectl create secret generic mysecret --dry-run=client --from-literal=foo=bar -o yaml > mysecret.yaml
```

kubernetes generated `mysecret.yaml`

## native kubernetes secret encoded by base64

```
cat mysecret.yaml
```

## seal secret with kubeseal 

check sealed secrets controller name in the cluster
```
kubectl get deployment -A | grep -i sealed-secrets
```
suppose your controller name `sealed-secrets-controller`

```
cat mysecret.yaml | kubeseal --controller-namespace kube-system --controller-name sealed-secrets-controller --format yaml > sealed-mysecret.yaml  
```

deploy sealed secret in cluster
```
kubectl apply -f sealed-mysecret.yaml
```