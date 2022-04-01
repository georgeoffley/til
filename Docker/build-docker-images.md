# Build Docker Images

[Source](https://docs.docker.com/engine/reference/commandline/build/)

```bash
docker build -t docker-app-image .
```

## Command Breakdown

- `docker build` - docker command
- `-t` - tag option for creating tag name
- `docker-app-image` - tag name
- `.` - directory where the dockerfile is located, in this instance we're running the command in the current directory