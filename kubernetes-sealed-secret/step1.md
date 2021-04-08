# Installing the kubeseal client

Sealed Secrets is composed of two parts:

1. A client-side utility: `kubeseal`
2. A cluster-side controller / operator


### First Part 
let's install client side tool first `kubeseal`

For Linux x86_64 systems, the client-tool may be installed into /usr/local/bin with the following command:

```
wget https://github.com/bitnami-labs/sealed-secrets/releases/download/v0.15.0/kubeseal-linux-amd64 -O kubeseal

sudo install -m 755 kubeseal /usr/local/bin/kubeseal
```

verify installation

```
kubeseal --version 
```

You should be able to see kubeseal client version as `v0.15.0` 