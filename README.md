# Cluster Ingress

A simple, homemade ingress for my k8s cluster, because I can't seem to wrap my head around the standard one and I know nginx really well.

## Port Forwarding

The following port forwarding rules need to be on the router

```
Local 31101 -> External 80
Local 31100 -> External 443
```