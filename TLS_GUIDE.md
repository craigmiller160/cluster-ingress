# TLS Certificate Guide

This is a simple guide to setting up a legit, valid, public TLS cert for the ingress. This uses Let's Encrypt.

It's very important that the app is running and the public domain is setup properly. If not, this will fail.

## Use Certbot

Certbot is a terminal application provided by Let's Encrypt. It can be installed on the Ubuntu-derived version of Linux using snap:

```
sudo snap install --classic certbot
```

Then, you need to register with certbot before anything else:

```
sudo certbot register
```

Then, it's time to generate the certificate. We just want the cert, nothing fancy:

```
sudo certbot certonly --manual
```

This will first ask for the domain name `craigmiller160.ddns.net`. Then, it'll offer a long, encoded string that has to be placed on the server and returned at the endpoint `/.well-known/acme-challenge/########`.

Then, put the authcode into the authcode file at `/opt/kubernetes/data/ingress/authcode/authcode.txt`. This will automatically expose it via the ingress API.

Please validate that you get the code back from the endpoint, as you only get 5 tries per-hour.

Once it is deployed and ready, click "enter" to proceed. Let's Encrypt will validate the code, and then issue the certificates in these directories on your machine:

```
# Certificate
/etc/letsencrypt/live/craigmiller160.ddns.net/fullchain.pem
# Key
/etc/letsencrypt/live/craigmiller160.ddns.net/privkey.pem
```

## Deploy Certs to Nginx

There is a directory that is mounted as a k8s volume:

```
/opt/kubernetes/data/ingress/cert
```

Simply copy the `fullchain.pem` and `privkey.pem` to this location.

## Renewing Certificates

I only know how to do this manually, so just repeat the above steps.