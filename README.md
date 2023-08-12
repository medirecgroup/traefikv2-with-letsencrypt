# traefikv2-with-letsencrypt

![Image of Traefik Example1](https://i.imgur.com/KLhtbvY.png)

![Image of Traefik Example2](https://i.imgur.com/MuRpuYT.png)

## Encriptando la contraseña

Procederemos a modificar el archivo traefik_dynamic.toml, pero antes vamos a crear las credenciales para el dashboard. Introduciremos nuestro usuario y contraseña, el cual encriptaremos en https://www.htaccesstools.com/htpasswd-generator/ y agregamos el subdomain con el cual podremos acceder al dashboard.

## Corriendo el servidor

With docker-compose
--------------------------------------------------------
docker-compose up -d

With docker run
--------------------------------------------------------
docker network create web

docker run -d \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v $PWD/traefik.toml:/traefik.toml \
  -v $PWD/traefik_dynamic.toml:/traefik_dynamic.toml \
  -v $PWD/acme.json:/acme.json \
  -p 80:80 \
  -p 443:443 \
  --network web \
  --name traefik \
  traefik:v2.2

---------------------------------------------------------
Reference  https://www.digitalocean.com/community/tutorials/how-to-use-traefik-v2-as-a-reverse-proxy-for-docker-containers-on-ubuntu-20-04