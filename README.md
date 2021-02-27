# Cluster Ingress

A simple, homemade ingress for my k8s cluster, because I can't seem to wrap my head around the standard one and I know nginx really well.

## Setup

The following directories are mounted as k8s volumes and need to exist:

```
/opt/kubernetes/data/ingress/cert
/opt/kubernetes/data/ingress/authcode
```

TLS certs need to go in the `cert` directory. They should be the Let's Encrypt certs from the TLS guide.

The authcode used for validating with Let's Encrypt goes in the `authcode` directory.

## Port Forwarding

The following port forwarding rules need to be on the router

```
Local 31101 -> External 80
Local 31100 -> External 443
```

## Public Domain Name

A public domain name has been acquired from No-IP, `craigmiller160.ddns.net`. This will be the host of this ingress and all the applications it connects to.

## Deploying

Just run the `kube-deploy` script.