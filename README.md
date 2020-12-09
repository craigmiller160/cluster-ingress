# Cluster Ingress

A simple, homemade ingress for my k8s cluster, because I can't seem to wrap my head around the standard one and I know nginx really well.

## Port Forwarding

The following port forwarding rules need to be on the router

```
Local 31101 -> External 80
Local 31100 -> External 443
```

## Public Domain Name

A public domain name has been acquired from No-IP, `craigmiller160.ddns.net`. This will be the host of this ingress and all the applications it connects to.