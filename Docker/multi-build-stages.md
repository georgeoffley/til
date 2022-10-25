# Multi Build Stages In Docker

[Sources](https://docs.docker.com/develop/develop-images/multistage-build/)

Using build stages you can set up Docker images to different options in the same `Dockerfile`.

## Example

```Dockerfile
FROM node:16.13-alpine as base
ARG version
WORKDIR /app
COPY package.json /app/
[[COPY]] yarn.lock /app/
RUN yarn install
ENV PATH /app/node_modules/.bin:$PATH
COPY . /app/

FROM node:16.13-alpine as build
ARG version
WORKDIR /app
COPY --from=base /app /app/
RUN NODE_ENV=production yarn build
```

In above `Dockerfile` you can see we've created two build stages, `base` and `build`. Each one has some different options but they live in the same `Dockerfile`. You can create these target builds using the `FROM ... AS base` syntax, which names the target to be referenced by the `docker-compose.yml`.

This is useful when creating a `docker-compose` network and you have `Dockerfiles` in the different root project directories.

You can utilize these build stages using the following syntax in your `docker-compose.yml`

```yml
    frontend:
    build:
        context: frontend
        target: base
    ...

    dist:
    build:
        context: frontend
        target: production
    ...
```

Using the `build` block with the `context`  we point to the dir to look for `Dockerfile` and then using the `target` key we point Docker to the correct build stage in the `Dockerfile`.

#Docker