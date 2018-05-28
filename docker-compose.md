# docker-compose
Define and run multi-container applications with Docker.

```bash
docker-compose [-f <arg>...] [options] [COMMAND] [ARGS...]
docker-compose -h|--help
```

#### Options: 

Options | Description 
----------------------------- | ----------------------------------------- 
`-f, --file FILE`             | Specify an alternate compose file (default: docker-compose.yml) 
`-p, --project-name NAME`     | Specify an alternate project name (default: directory name) 
`--verbose`                   | Show more output 
`--log-level LEVEL`           | Set log level (DEBUG, INFO, WARNING, ERROR, CRITICAL) 
`--no-ansi`                   | Do not print ANSI control characters 
`-v, --version`               | Print version and exit 
`-H, --host HOST`             | Daemon socket to connect to 
`--tls`                       | Use TLS; implied by --tlsverify 
`--tlscacert CA_PATH`         | Trust certs signed only by this CA 
`--tlscert CLIENT_CERT_PATH`  | Path to TLS certificate file 
`--tlskey TLS_KEY_PATH`       | Path to TLS key file 
`--tlsverify`                 | Use TLS and verify the remote 
`--skip-hostname-check`       | Don't check the daemon's hostname against the name specified in the client certificate 
`--project-directory PATH`    | Specify an alternate working directory (default: the path of the Compose file) 
`--compatibility`             | If set, Compose will attempt to convert deploy keys in v3 files to their non-Swarm equivalent 


### Commands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 <nobr>[`docker-compose build`](#docker-compose-build)</nobr> | Build or rebuild services. Services are built once and then tagged as `project_service`, e.g. `composetest_db`. If you change a service's `Dockerfile` or the contents of its build directory, you can run `docker-compose build` to rebuild it. 
 <nobr>[`docker-compose bundle`](#docker-compose-bundle)</nobr> | Generate a Distributed Application Bundle (DAB) from the Compose file. Images must have digests stored, which requires interaction with a Docker registry. If digests aren't stored for all images, you can fetch them with `docker-compose pull` or `docker-compose push`. To push images automatically when bundling, pass `--push-images`. Only services with a `build` option specified will have their images pushed. 
 <nobr>[`docker-compose config`](#docker-compose-config)</nobr> | Validate and view the Compose file. 
 <nobr>[`docker-compose create`](#docker-compose-create)</nobr> | Creates containers for a service. This command is deprecated. Use the `up` command with `--no-start` instead. 
 <nobr>[`docker-compose down`](#docker-compose-down)</nobr> | Stops containers and removes containers, networks, volumes, and images created by `up`. By default, the only things removed are: - Containers for services defined in the Compose file - Networks defined in the `networks` section of the Compose file - The default network, if one is used Networks and volumes defined as `external` are never removed. 
 <nobr>[`docker-compose events`](#docker-compose-events)</nobr> | Receive real time events from containers. 
 <nobr>[`docker-compose exec`](#docker-compose-exec)</nobr> | Execute a command in a running container 
 <nobr>[`docker-compose help`](#docker-compose-help)</nobr> | Get help on a command. 
 <nobr>[`docker-compose images`](#docker-compose-images)</nobr> | List images used by the created containers. Usage: images [options] [SERVICE...] 
 <nobr>[`docker-compose kill`](#docker-compose-kill)</nobr> | Force stop service containers. 
 <nobr>[`docker-compose logs`](#docker-compose-logs)</nobr> | View output from containers. 
 <nobr>[`docker-compose pause`](#docker-compose-pause)</nobr> | Pause services. 
 <nobr>[`docker-compose port`](#docker-compose-port)</nobr> | Print the public port for a port binding. 
 <nobr>[`docker-compose ps`](#docker-compose-ps)</nobr> | List containers. 
 <nobr>[`docker-compose pull`](#docker-compose-pull)</nobr> | Pulls images for services defined in a Compose file, but does not start the containers. 
 <nobr>[`docker-compose push`](#docker-compose-push)</nobr> | Pushes images for services. 
 <nobr>[`docker-compose restart`](#docker-compose-restart)</nobr> | Restart running containers. 
 <nobr>[`docker-compose rm`](#docker-compose-rm)</nobr> | Removes stopped service containers. By default, anonymous volumes attached to containers will not be removed. You can override this with `-v`. To list all volumes, use `docker volume ls`. Any data which is not in a volume will be lost. 
 <nobr>[`docker-compose run`](#docker-compose-run)</nobr> | Run a one-off command on a service. 
 <nobr>[`docker-compose scale`](#docker-compose-scale)</nobr> | Set number of containers to run for a service. Numbers are specified in the form `service=num` as arguments. For example:     $ docker-compose scale web=2 worker=3 This command is deprecated. Use the up command with the `--scale` flag instead. 
 <nobr>[`docker-compose start`](#docker-compose-start)</nobr> | Start existing containers. 
 <nobr>[`docker-compose stop`](#docker-compose-stop)</nobr> | Stop running containers without removing them. They can be started again with `docker-compose start`. 
 <nobr>[`docker-compose top`](#docker-compose-top)</nobr> | Display the running processes 
 <nobr>[`docker-compose unpause`](#docker-compose-unpause)</nobr> | Unpause services. 
 <nobr>[`docker-compose up`](#docker-compose-up)</nobr> | Builds, (re)creates, starts, and attaches to containers for a service. Unless they are already running, this command also starts any linked services. The `docker-compose up` command aggregates the output of each container. When the command exits, all containers are stopped. Running `docker-compose up -d` starts the containers in the background and leaves them running. If there are existing containers for a service, and the service's configuration or image was changed after the container's creation, `docker-compose up` picks up the changes by stopping and recreating the containers (preserving mounted volumes). To prevent Compose from picking up changes, use the `--no-recreate` flag. If you want to force Compose to stop and recreate all containers, use the `--force-recreate` flag. 
 <nobr>[`docker-compose version`](#docker-compose-version)</nobr> | Show version informations 


## docker-compose build
Build or rebuild services.
Services are built once and then tagged as `project_service`,
e.g. `composetest_db`. If you change a service's `Dockerfile` or the
contents of its build directory, you can run `docker-compose build` to rebuild it.

```bash
build [options] [--build-arg key=val...] [SERVICE...]
```

#### Options: 

Options | Description 
--------------------------- | ------------------------------------------- 
`--compress`                | Compress the build context using gzip. 
`--force-rm`                | Always remove intermediate containers. 
`--no-cache`                | Do not use cache when building the image. 
`--pull`                    | Always attempt to pull a newer version of the image. 
`-m, --memory MEM`          | Sets memory limit for the build container. 
`--build-arg key=val`       | Set build-time variables for services. 



-----
## docker-compose bundle
Generate a Distributed Application Bundle (DAB) from the Compose file.
Images must have digests stored, which requires interaction with a
Docker registry. If digests aren't stored for all images, you can fetch
them with `docker-compose pull` or `docker-compose push`. To push images
automatically when bundling, pass `--push-images`. Only services with
a `build` option specified will have their images pushed.

```bash
bundle [options]
```

#### Options: 

Options | Description 
------------------------------ | ---------------------------------------- 
`--push-images`                | Automatically push images for any services which have a `build` option specified. 
`-o, --output PATH`            | Path to write the bundle file to. Defaults to "&#60;project name&#62;.dab". 



-----
## docker-compose config
Validate and view the Compose file.

```bash
config [options]
```

#### Options: 

Options | Description 
---------------------------- | ------------------------------------------ 
`--resolve-image-digests`    | Pin image tags to digests. 
`-q, --quiet`                | Only validate the configuration, don't print anything. 
`--services`                 | Print the service names, one per line. 
`--volumes`                  | Print the volume names, one per line. 



-----
## docker-compose create
Creates containers for a service.
This command is deprecated. Use the `up` command with `--no-start` instead.

```bash
create [options] [SERVICE...]
```

#### Options: 

Options | Description 
-------------------------- | -------------------------------------------- 
`--force-recreate`         | Recreate containers even if their configuration and image haven't changed. Incompatible with --no-recreate. 
`--no-recreate`            | If containers already exist, don't recreate them. Incompatible with --force-recreate. 
`--no-build`               | Don't build an image, even if it's missing. 
`--build`                  | Build images before creating containers. 



-----
## docker-compose down
Stops containers and removes containers, networks, volumes, and images
created by `up`.
By default, the only things removed are:
- Containers for services defined in the Compose file
- Networks defined in the `networks` section of the Compose file
- The default network, if one is used
Networks and volumes defined as `external` are never removed.

```bash
down [options]
```

#### Options: 

Options | Description 
--------------------------- | ------------------------------------------- 
`--rmi type`                | Remove images. Type must be one of: 'all': Remove all images used by any service. 'local': Remove only images that don't have a custom tag set by the `image` field. 
`-v, --volumes`             | Remove named volumes declared in the `volumes` section of the Compose file and anonymous volumes attached to containers. 
`--remove-orphans`          | Remove containers for services not defined in the Compose file 
`-t, --timeout TIMEOUT`     | Specify a shutdown timeout in seconds. (default: 10) 



-----
## docker-compose events
Receive real time events from containers.

```bash
events [options] [SERVICE...]
```

#### Options: 

Options | Description 
--------------- | ------------------------------------------------------- 
`--json`        | Output events as a stream of json objects 



-----
## docker-compose exec
Execute a command in a running container

```bash
exec [options] [-e KEY=VAL...] SERVICE COMMAND [ARGS...]
```

#### Options: 

Options | Description 
--------------------- | ------------------------------------------------- 
`-d, --detach`        | Detached mode: Run command in the background. 
`--privileged`        | Give extended privileges to the process. 
`-u, --user USER`     | Run the command as this user. 
`-T`                  | Disable pseudo-tty allocation. By default `docker-compose exec` allocates a TTY. 
`--index=index`       | index of the container if there are multiple instances of a service [default: 1] 
`-e, --env KEY=VAL`   | Set environment variables (can be used multiple times, not supported in API &#60; 1.25) 
`-w, --workdir DIR`   | Path to workdir directory for this command. 



-----
## docker-compose help
Get help on a command.

```bash
help [COMMAND]
```


-----
## docker-compose images
List images used by the created containers.
Usage: images [options] [SERVICE...]

#### Options: 

Options | Description 
---------------- | ------------------------------------------------------ 
`-q, --quiet`    | Only display IDs 



-----
## docker-compose kill
Force stop service containers.

```bash
kill [options] [SERVICE...]
```

#### Options: 

Options | Description 
--------------------- | ------------------------------------------------- 
`-s SIGNAL`           | SIGNAL to send to the container. Default signal is SIGKILL. 



-----
## docker-compose logs
View output from containers.

```bash
logs [options] [SERVICE...]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`--no-color`            | Produce monochrome output. 
`-f, --follow`          | Follow log output. 
`-t, --timestamps`      | Show timestamps. 
`--tail="all"`          | Number of lines to show from the end of the logs for each container. 



-----
## docker-compose pause
Pause services.

```bash
pause [SERVICE...]
```


-----
## docker-compose port
Print the public port for a port binding.

```bash
port [options] SERVICE PRIVATE_PORT
```

#### Options: 

Options | Description 
--------------------- | ------------------------------------------------- 
`--protocol=proto`    | tcp or udp [default: tcp] 
`--index=index`       | index of the container if there are multiple instances of a service [default: 1] 



-----
## docker-compose ps
List containers.

```bash
ps [options] [SERVICE...]
```

#### Options: 

Options | Description 
------------------------ | ---------------------------------------------- 
`-q, --quiet`            | Only display IDs 
`--services`             | Display services 
`--filter KEY=VAL`       | Filter services by a property 



-----
## docker-compose pull
Pulls images for services defined in a Compose file, but does not start the containers.

```bash
pull [options] [SERVICE...]
```

#### Options: 

Options | Description 
--------------------------- | ------------------------------------------- 
`--ignore-pull-failures`    | Pull what it can and ignores images with pull failures. 
`--parallel`                | Deprecated, pull multiple images in parallel (enabled by default). 
`--no-parallel`             | Disable parallel pulling. 
`-q, --quiet`               | Pull without printing progress information 
`--include-deps`            | Also pull services declared as dependencies 



-----
## docker-compose push
Pushes images for services.

```bash
push [options] [SERVICE...]
```

#### Options: 

Options | Description 
--------------------------- | ------------------------------------------- 
`--ignore-push-failures`    | Push what it can and ignores images with push failures. 



-----
## docker-compose restart
Restart running containers.

```bash
restart [options] [SERVICE...]
```

#### Options: 

Options | Description 
---------------------------- | ------------------------------------------ 
`-t, --timeout TIMEOUT`      | Specify a shutdown timeout in seconds. (default: 10) 



-----
## docker-compose rm
Removes stopped service containers.
By default, anonymous volumes attached to containers will not be removed. You
can override this with `-v`. To list all volumes, use `docker volume ls`.
Any data which is not in a volume will be lost.

```bash
rm [options] [SERVICE...]
```

#### Options: 

Options | Description 
----------------- | ----------------------------------------------------- 
`-f, --force`     | Don't ask to confirm removal 
`-s, --stop`      | Stop the containers, if required, before removing 
`-v`              | Remove any anonymous volumes attached to containers 
`-a, --all`       | Deprecated - no effect. 



-----
## docker-compose run
Run a one-off command on a service.

```bash
run [options] [-v VOLUME...] [-p PORT...] [-e KEY=VAL...] [-l KEY=VALUE...]
SERVICE [COMMAND] [ARGS...]
```

#### Options: 

Options | Description 
------------------------- | --------------------------------------------- 
`-d, --detach`            | Detached mode: Run container in the background, print new container name. 
`--name NAME`             | Assign a name to the container 
`--entrypoint CMD`        | Override the entrypoint of the image. 
`-e KEY=VAL`              | Set an environment variable (can be used multiple times) 
`-l, --label KEY=VAL`     | Add or override a label (can be used multiple times) 
`-u, --user=""`           | Run as specified username or uid 
`--no-deps`               | Don't start linked services. 
`--rm`                    | Remove container after run. Ignored in detached mode. 
`-p, --publish=[]`        | Publish a container's port(s) to the host 
`--service-ports`         | Run command with the service's ports enabled and mapped to the host. 
`--use-aliases`           | Use the service's network aliases in the network(s) the container connects to. 
`-v, --volume=[]`         | Bind mount a volume (default []) 
`-T`                      | Disable pseudo-tty allocation. By default `docker-compose run` allocates a TTY. 
`-w, --workdir=""`        | Working directory inside the container 



-----
## docker-compose scale
Set number of containers to run for a service.
Numbers are specified in the form `service=num` as arguments.
For example:   $ docker-compose scale web=2 worker=3
This command is deprecated. Use the up command with the `--scale` flag
instead.

```bash
scale [options] [SERVICE=NUM...]
```

#### Options: 

Options | Description 
---------------------------- | ------------------------------------------ 
`-t, --timeout TIMEOUT`      | Specify a shutdown timeout in seconds. (default: 10) 



-----
## docker-compose start
Start existing containers.

```bash
start [SERVICE...]
```


-----
## docker-compose stop
Stop running containers without removing them.
They can be started again with `docker-compose start`.

```bash
stop [options] [SERVICE...]
```

#### Options: 

Options | Description 
---------------------------- | ------------------------------------------ 
`-t, --timeout TIMEOUT`      | Specify a shutdown timeout in seconds. (default: 10) 



-----
## docker-compose top
Display the running processes

```bash
top [SERVICE...]
```


-----
## docker-compose unpause
Unpause services.

```bash
unpause [SERVICE...]
```


-----
## docker-compose up
Builds, (re)creates, starts, and attaches to containers for a service.
Unless they are already running, this command also starts any linked services.
The `docker-compose up` command aggregates the output of each container. When
the command exits, all containers are stopped. Running `docker-compose up -d`
starts the containers in the background and leaves them running.
If there are existing containers for a service, and the service's configuration
or image was changed after the container's creation, `docker-compose up` picks
up the changes by stopping and recreating the containers (preserving mounted
volumes). To prevent Compose from picking up changes, use the `--no-recreate`
flag.
If you want to force Compose to stop and recreate all containers, use the
`--force-recreate` flag.

```bash
up [options] [--scale SERVICE=NUM...] [SERVICE...]
```

#### Options: 

Options | Description 
------------------------------ | ---------------------------------------- 
`-d, --detach`                 | Detached mode: Run containers in the background, print new container names. Incompatible with --abort-on-container-exit. 
`--no-color`                   | Produce monochrome output. 
`--quiet-pull`                 | Pull without printing progress information 
`--no-deps`                    | Don't start linked services. 
`--force-recreate`             | Recreate containers even if their configuration and image haven't changed. 
`--always-recreate-deps`       | Recreate dependent containers. Incompatible with --no-recreate. 
`--no-recreate`                | If containers already exist, don't recreate them. Incompatible with --force-recreate and -V. 
`--no-build`                   | Don't build an image, even if it's missing. 
`--no-start`                   | Don't start the services after creating them. 
`--build`                      | Build images before starting containers. 
`--abort-on-container-exit`    | Stops all containers if any container was stopped. Incompatible with -d. 
`-t, --timeout TIMEOUT`        | Use this timeout in seconds for container shutdown when attached or when containers are already running. (default: 10) 
`-V, --renew-anon-volumes`     | Recreate anonymous volumes instead of retrieving data from the previous containers. 
`--remove-orphans`             | Remove containers for services not defined in the Compose file. 
`--exit-code-from SERVICE`     | Return the exit code of the selected service container. Implies --abort-on-container-exit. 
`--scale SERVICE=NUM`          | Scale SERVICE to NUM instances. Overrides the `scale` setting in the Compose file if present. 



-----
## docker-compose version
Show version informations

```bash
version [--short]
```

#### Options: 

Options | Description 
--------------- | ------------------------------------------------------- 
`--short`       | Shows only Compose's version number.