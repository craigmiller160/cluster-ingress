# TLS Certificate Guide

This is a simple guide to setting up a legit, valid, public TLS cert for the ingress. This uses Let's Encrypt.

It's very important that the app is running and the public domain is setup properly. If not, this will fail.

## Use Certbot

Certbot is a terminal application provided by Let's Encrypt. It can be installed on the Ubuntu-derived version of Linux using snap:

```
sudo snap install --classic certbot
```

Then, it's time to generate the certificate. We just want the cert, nothing fancy:

```
sudo certbot certonly
```