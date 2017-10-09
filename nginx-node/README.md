nginx-node
=============

Creates a docker image with NGINX and Node installed in it. Useful to serve up a single page application built with node.

## Usage

Make a `Dockerfile` something like this:

```bash
FROM sinet/nginx-node:latest

# Install and build the application
COPY . /usr/src/app
WORKDIR /usr/src/app
RUN yarn && yarn run start

COPY default.conf /etc/nginx/conf.d/

CMD ["nginx", "-g", "daemon off;"]
```

The `default.conf` would look something like this.

```
server {
    listen       80;
    server_name  localhost;

    location / {
        root   /usr/src/app/dist;
        index  index.html index.htm;
    }

}
```
