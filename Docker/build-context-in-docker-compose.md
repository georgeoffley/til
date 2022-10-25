# Building Context into Docker Compose

## Source
- [Source](https://docs.docker.com/compose/compose-file/compose-file-v3/#:~:text=images%20before%20deploying.-,context,sent%20to%20the%20Docker%20daemon.)

## Notes
- When creating a Docker Compose setup you can set set the context for building each node.

- Context, in this case, is setting the `docker-compose.yml` a place to look for a `Dockerfile`. So if I have multiple nodes each building a different way, I can create a `Dockerfile` for each one and store it at the root of the project subdirectory. I can set the context within the node's options to look in that directory for a `Dockerfile` and build the image for it there.

- Tha's not the only way to create a different image for each node, but it's one way to do it.

## Example

```yml
Version: 3
services:
  webapp:
    build:
      context: ./dir/webapproot
      dockerfile: DockerFile
```

In the above example we set the context and the name of the `Dockerfile`. Setting the context should be enough as Docker will always search for a file named `Dockerfile` but if you name a `Dockerfile` something else you can specify that here in the `dockerfile` option.

#Docker