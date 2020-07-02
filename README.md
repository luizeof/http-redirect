# HTTP redirect

Inspired by `ianneub/redirect`.

This docker image redirect all HTTP requests on port 80 to the root path specified in the `REDIRECT` environment variable with 301 Http status.

The ENV `REDIRECT` need to be populated with entire URI will be sent to the redirected path.

## Example with jwilder/nginx-proxy

```
bash docker run -d \
 -P \
 -e VIRTUAL_HOST="www.luizeof.com" \
 -e REDIRECT="https://luizeof.com" \
 --restart=always \
 luizeof/http-redirect
```

This will redirect all traffic from `www.luizeof.com` to `https://luizeof.com`.

This image also works with SSL on nginx-proxy-companion or some load balancer like traefik.
