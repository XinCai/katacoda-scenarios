# copy cert file to anywhere you like (e.g local pc)

seal your k8s secret on your laptop 
```
kubeseal --cert mycert.pem --format=yaml <mysecret.yaml > my-sealed-secret.yaml
```
check content
```
cat my-sealed-secret.yaml
```


