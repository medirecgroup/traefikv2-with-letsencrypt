touch acme.json

chmod 600 acme.json

docker network create web

docker-compose up -d

References:

- https://blog.saiyans.com.ve/2022/04/12/traefik-2/
- https://github.com/tomasmetal23/traefikv2-with-letsencrypt
- https://www.digitalocean.com/community/tutorials/how-to-use-traefik-v2-as-a-reverse-proxy-for-docker-containers-on-ubuntu-20-04
