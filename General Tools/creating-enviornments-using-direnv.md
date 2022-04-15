# Creating Environments Using Direnv

[Source](https://direnv.net/)

Direnv is an amazing tool which can used for setting up custom environments for your projects. The program is essentially a bash script which will run whenever you cd into the directory where the `.envrc` is located. For example you put it in the root of a project and set up needed things like environment variables. You can also use it to help create helper scripts for utilities you need in your project.

### Some Examples

Here is an `.envrc` file.

```bash {.line-numbers}
#!/usr/bin/env bash

# programming envs
export RBENV_VERSION="3.1.0"
export NODENV_VERSION="16.13.0"

# development environment
PATH_add bin

# add project ruby binaries to path
PATH_add backend/vendor/bundle/ruby/$RBENV_VERSION/bin

# add project javascript binaries to path
PATH_add frontend/node_modules/.bin

current_dir="$(pwd)"
export PROJECT_ROOT="$current_dir"
export PROJECT_NAME="combine"
export COMPOSE_PROJECT_NAME="$PROJECT_NAME"

# mysql connection
export MYSQL_PASSWORD="alpine"
export MYSQL_CONNECTION="mysql2://root:$MYSQL_PASSWORD@db:3306"
```

Let's go through some explainers.

In the top section you can see we run bash commands to create needed environment variables. You can essentially run any needed bash commands specific to a project when you cd into that directory.

Below that on line 8, you can also add paths to your path. Which is just another bash command. We used this in conjunction with a `/bin` directory and created some needed scripts for running the project. For example we had a script for killing all your running docker containers, pruning the containers, and then pruning volumes. Which helped us clean everything out when we made changes to a project. You can see the script below.

```bash
#!/usr/bin/env bash

docker kill "$(docker ps -qa)"    # kills all your docker processes
docker system prune               # cleans up old docker networks, containers, caches
docker volume prune               # deletes all volumes
```

Using direnv with this allowed us to just run `dprune` in our local development environments. 

On line 14 you can also see that we add in binaries into our path. Depending on our setup, we might need to do that. For example in a Python project we can use this to add the Python Path into our path for easier importing of modules. 

You might also notice that on line 22, you can set environment variables needed for certain projects. In this case we set the MySQL connection and password which the local MySQL setup will be looking for when it starts up. In our case we used these in our `Dockerfiles` for `docker-compose.yml` to set all our need environment variables for use in our projects.

There's really no limit to what you can do to make your development environment easier to use. 

### Notes

Great project, but very Linux specific. I was not able to get it working in Windows unless I created the project and ran everything in the Windows Linux Subsystem. Or use a Mac.