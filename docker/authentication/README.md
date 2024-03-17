# Authentication w/ Authelia, NGINX Proxy Manager and LLDAP

Authelia (Advanced Config)

```conf

location / {
    include /snippets/proxy.conf;
    proxy_pass $forward_scheme://$server:$port;
}

```

Config for services that'll need authentication

```conf

include /snippets/authelia-location.conf;

location / {
    include /snippets/proxy.conf;
    include /snippets/authelia-authrequest.conf;
    proxy_pass $forward_scheme://$server:$port;
}

```
