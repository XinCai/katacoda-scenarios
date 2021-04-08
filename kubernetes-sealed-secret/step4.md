## Share Public key / Certificate 
The key certificate (public key portion) is used for sealing secrets, and needs to be available wherever kubeseal is going to be used. The certificate is not secret information, although you need to ensure you are using the correct one.

`kubeseal` will fetch the certificate from the controller at runtime (requires secure access to the Kubernetes API server), which is convenient for interactive use, but it's known to be brittle when users have clusters with special configurations such as private GKE clusters that have firewalls between master and nodes.

An alternative workflow is to store the certificate somewhere (e.g. local disk) with kubeseal --fetch-cert >mycert.pem, and use it offline with `kubeseal --cert mycert.pem`. The certificate is also printed to the controller log on startup.

let's export public key as `mycert.pem` file 

```
kubeseal --fetch-cert >mycert.pem
```


