# Docker Run Command

[Source](https://docs.docker.com/engine/reference/commandline/run/)

```bash
docker run -it --rm --name dockercontainer
```

## Command Breakdown

- `docker run` - Docker run command.
- `-it` - Instructs docker to allocate a pseudo TTY and to run in interactive mode which keeps STDIN open even if not attached.
- `--rm` - Automatically remove container when it exits.
- `--name` - Name flag, the following argument will be the name of the container.
- `dockercontainer` - The name of the container to pass into Docker.