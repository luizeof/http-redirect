# HTTP redirect

Inspired by `ianneub/redirect`.

This docker image redirect all HTTP requests on port 80 to the root path specified in the `REDIRECT` environment variable with 301 Http status.

The ENV `REDIRECT` need to be populated with entire URI will be sent to the redirected path.

## Example with jwilder/nginx-proxy

```
bash docker run -d \
 -P \
 -e REDIRECT="https://luizeof.com.br" \
 -e VIRTUAL_HOST="www.luizeof.com.br" \
 --restart=always \
 ianneub/redirect
```

This will redirect all traffic from `www.luizeof.com.br` to `https://luizeof.com.br/`.

This image also works with SSL on nginx-proxy-companion or some load balancer like traefik.
