# docker
A self-sufficient runtime for containers

```bash
docker COMMAND
```

#### Options: 

Options | Description 
-------------------------- | -------------------------------------------- 
`--config string`          | Location of client config files (default "~/.docker") 
`-D, --debug`              | Enable debug mode 
`-H, --host list`          | Daemon socket(s) to connect to 
`-l, --log-level string`   | Set the logging level ("debug"&#124;"info"&#124;"warn"&#124;"error"&#124;"fatal") (default "info") 
`--tls`                    | Use TLS; implied by --tlsverify 
`--tlscacert string`       | Trust certs signed only by this CA (default "~/.docker/ca.pem") 
`--tlscert string`         | Path to TLS certificate file (default "~/.docker/cert.pem") 
`--tlskey string`          | Path to TLS key file (default "~/.docker/key.pem") 
`--tlsverify`              | Use TLS and verify the remote 
`-v, --version`            | Print version information and quit 


### Management Commands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 `docker checkpoint`       | Manage checkpoints 
 `docker config`           | Manage Docker configs 
 `docker container`        | Manage containers 
 `docker image`            | Manage images 
 `docker network`          | Manage networks 
 `docker node`             | Manage Swarm nodes 
 `docker plugin`           | Manage plugins 
 `docker secret`           | Manage Docker secrets 
 `docker service`          | Manage services 
 `docker swarm`            | Manage Swarm 
 `docker system`           | Manage Docker 
 `docker trust`            | Manage trust on Docker images 
 `docker volume`           | Manage volumes 


### Commands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 `docker attach`           | Attach local standard input, output, and error streams to a running container 
 `docker build`            | Build an image from a Dockerfile 
 `docker commit`           | Create a new image from a container's changes 
 `docker cp`               | Copy files/folders between a container and the local filesystem 
 `docker create`           | Create a new container 
 `docker deploy`           | Deploy a new stack or update an existing stack 
 `docker diff`             | Inspect changes to files or directories on a container's filesystem 
 `docker events`           | Get real time events from the server 
 `docker exec`             | Run a command in a running container 
 `docker export`           | Export a container's filesystem as a tar archive 
 `docker history`          | Show the history of an image 
 `docker images`           | List images 
 `docker import`           | Import the contents from a tarball to create a filesystem image 
 `docker info`             | Display system-wide information 
 `docker inspect`          | Return low-level information on Docker objects 
 `docker kill`             | Kill one or more running containers 
 `docker load`             | Load an image from a tar archive or STDIN 
 `docker login`            | Log in to a Docker registry 
 `docker logout`           | Log out from a Docker registry 
 `docker logs`             | Fetch the logs of a container 
 `docker pause`            | Pause all processes within one or more containers 
 `docker port`             | List port mappings or a specific mapping for the container 
 `docker ps`               | List containers 
 `docker pull`             | Pull an image or a repository from a registry 
 `docker push`             | Push an image or a repository to a registry 
 `docker rename`           | Rename a container 
 `docker restart`          | Restart one or more containers 
 `docker rm`               | Remove one or more containers 
 `docker rmi`              | Remove one or more images 
 `docker run`              | Run a command in a new container 
 `docker save`             | Save one or more images to a tar archive (streamed to STDOUT by default) 
 `docker search`           | Search the Docker Hub for images 
 `docker start`            | Start one or more stopped containers 
 `docker stats`            | Display a live stream of container(s) resource usage statistics 
 `docker stop`             | Stop one or more running containers 
 `docker tag`              | Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE 
 `docker top`              | Display the running processes of a container 
 `docker unpause`          | Unpause all processes within one or more containers 
 `docker update`           | Update configuration of one or more containers 
 `docker version`          | Show the Docker version information 
 `docker wait`             | Block until one or more containers stop, then print their exit codes 


## docker checkpoint
Manage checkpoints

```bash
docker checkpoint COMMAND
```

### Commands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 `docker checkpoint create` | Create a checkpoint from a running container 
 `docker checkpoint ls`    | List checkpoints for a container 
 `docker checkpoint rm`    | Remove a checkpoint 


### docker checkpoint create
Create a checkpoint from a running container

```bash
docker checkpoint create [OPTIONS] CONTAINER CHECKPOINT
```

#### Options: 

Options | Description 
------------------------------- | --------------------------------------- 
`--checkpoint-dir string`       | Use a custom checkpoint storage directory 
`--leave-running`               | Leave the container running after checkpoint 



-----
### docker checkpoint ls
List checkpoints for a container

```bash
docker checkpoint ls [OPTIONS] CONTAINER
```

#### Options: 

Options | Description 
------------------------------- | --------------------------------------- 
`--checkpoint-dir string`       | Use a custom checkpoint storage directory 



-----
### docker checkpoint rm
Remove a checkpoint

```bash
docker checkpoint rm [OPTIONS] CONTAINER CHECKPOINT
```

#### Options: 

Options | Description 
------------------------------- | --------------------------------------- 
`--checkpoint-dir string`       | Use a custom checkpoint storage directory 



-----
## docker config
Manage Docker configs

```bash
docker config COMMAND
```

### Commands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 `docker config create`    | Create a config from a file or STDIN 
 `docker config inspect`   | Display detailed information on one or more configs 
 `docker config ls`        | List configs 
 `docker config rm`        | Remove one or more configs 


### docker config create
Create a config from a file or STDIN

```bash
docker config create [OPTIONS] CONFIG file|-
```

#### Options: 

Options | Description 
-------------------------------- | -------------------------------------- 
`-l, --label list`               | Config labels 
`--template-driver string`       | Template driver 



-----
### docker config inspect
Display detailed information on one or more configs

```bash
docker config inspect [OPTIONS] CONFIG [CONFIG...]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --format string`   | Format the output using the given Go template 
`--pretty`              | Print the information in a human friendly format 



-----
### docker config ls
List configs

```bash
docker config ls [OPTIONS]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --filter filter`   | Filter output based on conditions provided 
`--format string`       | Pretty-print configs using a Go template 
`-q, --quiet`           | Only display IDs 



-----
### docker config rm
Remove one or more configs

```bash
docker config rm CONFIG [CONFIG...]
```


-----
## docker container
Manage containers

```bash
docker container COMMAND
```

### Commands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 `docker container attach` | Attach local standard input, output, and error streams to a running container 
 `docker container commit` | Create a new image from a container's changes 
 `docker container cp`     | Copy files/folders between a container and the local filesystem 
 `docker container create` | Create a new container 
 `docker container diff`   | Inspect changes to files or directories on a container's filesystem 
 `docker container exec`   | Run a command in a running container 
 `docker container export` | Export a container's filesystem as a tar archive 
 `docker container inspect` | Display detailed information on one or more containers 
 `docker container kill`   | Kill one or more running containers 
 `docker container logs`   | Fetch the logs of a container 
 `docker container ls`     | List containers 
 `docker container pause`  | Pause all processes within one or more containers 
 `docker container port`   | List port mappings or a specific mapping for the container 
 `docker container prune`  | Remove all stopped containers 
 `docker container rename` | Rename a container 
 `docker container restart` | Restart one or more containers 
 `docker container rm`     | Remove one or more containers 
 `docker container run`    | Run a command in a new container 
 `docker container start`  | Start one or more stopped containers 
 `docker container stats`  | Display a live stream of container(s) resource usage statistics 
 `docker container stop`   | Stop one or more running containers 
 `docker container top`    | Display the running processes of a container 
 `docker container unpause` | Unpause all processes within one or more containers 
 `docker container update` | Update configuration of one or more containers 
 `docker container wait`   | Block until one or more containers stop, then print their exit codes 


### docker container attach
Attach local standard input, output, and error streams to a running container

```bash
docker container attach [OPTIONS] CONTAINER
```

#### Options: 

Options | Description 
---------------------------- | ------------------------------------------ 
`--detach-keys string`       | Override the key sequence for detaching a container 
`--no-stdin`                 | Do not attach STDIN 
`--sig-proxy`                | Proxy all received signals to the process (default true) 



-----
### docker container commit
Create a new image from a container's changes

```bash
docker container commit [OPTIONS] CONTAINER [REPOSITORY[:TAG]]
```

#### Options: 

Options | Description 
------------------------ | ---------------------------------------------- 
`-a, --author string`    | Author (e.g., "John Hannibal Smith &#60;hannibal&#64;a-team.com&#62;") 
`-c, --change list`      | Apply Dockerfile instruction to the created image 
`-m, --message string`   | Commit message 
`-p, --pause`            | Pause container during commit (default true) 



-----
### docker container cp
Copy files/folders between a container and the local filesystem

```bash
docker container cp [OPTIONS] CONTAINER:SRC_PATH DEST_PATH|-
```

#### Options: 

Options | Description 
--------------------- | ------------------------------------------------- 
`-a, --archive`       | Archive mode (copy all uid/gid information) 
`-L, --follow-link`   | Always follow symbol link in SRC_PATH 



-----
### docker container create
Create a new container

```bash
docker container create [OPTIONS] IMAGE [COMMAND] [ARG...]
```

#### Options: 

Options | Description 
-------------------------------------- | -------------------------------- 
`--add-host list`                      | Add a custom host-to-IP mapping (host:ip) 
`-a, --attach list`                    | Attach to STDIN, STDOUT or STDERR 
`--blkio-weight uint16`                | Block IO (relative weight), between 10 and 1000, or 0 to disable (default 0) 
`--blkio-weight-device list`           | Block IO weight (relative device weight) (default []) 
`--cap-add list`                       | Add Linux capabilities 
`--cap-drop list`                      | Drop Linux capabilities 
`--cgroup-parent string`               | Optional parent cgroup for the container 
`--cidfile string`                     | Write the container ID to the file 
`--cpu-period int`                     | Limit CPU CFS (Completely Fair Scheduler) period 
`--cpu-quota int`                      | Limit CPU CFS (Completely Fair Scheduler) quota 
`--cpu-rt-period int`                  | Limit CPU real-time period in microseconds 
`--cpu-rt-runtime int`                 | Limit CPU real-time runtime in microseconds 
`-c, --cpu-shares int`                 | CPU shares (relative weight) 
`--cpus decimal`                       | Number of CPUs 
`--cpuset-cpus string`                 | CPUs in which to allow execution (0-3, 0,1) 
`--cpuset-mems string`                 | MEMs in which to allow execution (0-3, 0,1) 
`--device list`                        | Add a host device to the container 
`--device-cgroup-rule list`            | Add a rule to the cgroup allowed devices list 
`--device-read-bps list`               | Limit read rate (bytes per second) from a device (default []) 
`--device-read-iops list`              | Limit read rate (IO per second) from a device (default []) 
`--device-write-bps list`              | Limit write rate (bytes per second) to a device (default []) 
`--device-write-iops list`             | Limit write rate (IO per second) to a device (default []) 
`--disable-content-trust`              | Skip image verification (default true) 
`--dns list`                           | Set custom DNS servers 
`--dns-option list`                    | Set DNS options 
`--dns-search list`                    | Set custom DNS search domains 
`--entrypoint string`                  | Overwrite the default ENTRYPOINT of the image 
`-e, --env list`                       | Set environment variables 
`--env-file list`                      | Read in a file of environment variables 
`--expose list`                        | Expose a port or a range of ports 
`--group-add list`                     | Add additional groups to join 
`--health-cmd string`                  | Command to run to check health 
`--health-interval duration`           | Time between running the check (ms&#124;s&#124;m&#124;h) (default 0s) 
`--health-retries int`                 | Consecutive failures needed to report unhealthy 
`--health-start-period duration`       | Start period for the container to initialize before starting health-retries countdown (ms&#124;s&#124;m&#124;h) (default 0s) 
`--health-timeout duration`            | Maximum time to allow one check to run (ms&#124;s&#124;m&#124;h) (default 0s) 
`--help`                               | Print usage 
`-h, --hostname string`                | Container host name 
`--init`                               | Run an init inside the container that forwards signals and reaps processes 
`-i, --interactive`                    | Keep STDIN open even if not attached 
`--ip string`                          | IPv4 address (e.g., 172.30.100.104) 
`--ip6 string`                         | IPv6 address (e.g., 2001:db8::33) 
`--ipc string`                         | IPC mode to use 
`--isolation string`                   | Container isolation technology 
`--kernel-memory bytes`                | Kernel memory limit 
`-l, --label list`                     | Set meta data on a container 
`--label-file list`                    | Read in a line delimited file of labels 
`--link list`                          | Add link to another container 
`--link-local-ip list`                 | Container IPv4/IPv6 link-local addresses 
`--log-driver string`                  | Logging driver for the container 
`--log-opt list`                       | Log driver options 
`--mac-address string`                 | Container MAC address (e.g., 92:d0:c6:0a:29:33) 
`-m, --memory bytes`                   | Memory limit 
`--memory-reservation bytes`           | Memory soft limit 
`--memory-swap bytes`                  | Swap limit equal to memory plus swap: '-1' to enable unlimited swap 
`--memory-swappiness int`              | Tune container memory swappiness (0 to 100) (default -1) 
`--mount mount`                        | Attach a filesystem mount to the container 
`--name string`                        | Assign a name to the container 
`--network string`                     | Connect a container to a network (default "default") 
`--network-alias list`                 | Add network-scoped alias for the container 
`--no-healthcheck`                     | Disable any container-specified HEALTHCHECK 
`--oom-kill-disable`                   | Disable OOM Killer 
`--oom-score-adj int`                  | Tune host's OOM preferences (-1000 to 1000) 
`--pid string`                         | PID namespace to use 
`--pids-limit int`                     | Tune container pids limit (set -1 for unlimited) 
`--platform string`                    | Set platform if server is multi-platform capable 
`--privileged`                         | Give extended privileges to this container 
`-p, --publish list`                   | Publish a container's port(s) to the host 
`-P, --publish-all`                    | Publish all exposed ports to random ports 
`--read-only`                          | Mount the container's root filesystem as read only 
`--restart string`                     | Restart policy to apply when a container exits (default "no") 
`--rm`                                 | Automatically remove the container when it exits 
`--runtime string`                     | Runtime to use for this container 
`--security-opt list`                  | Security Options 
`--shm-size bytes`                     | Size of /dev/shm 
`--stop-signal string`                 | Signal to stop a container (default "SIGTERM") 
`--stop-timeout int`                   | Timeout (in seconds) to stop a container 
`--storage-opt list`                   | Storage driver options for the container 
`--sysctl map`                         | Sysctl options (default map[]) 
`--tmpfs list`                         | Mount a tmpfs directory 
`-t, --tty`                            | Allocate a pseudo-TTY 
`--ulimit ulimit`                      | Ulimit options (default []) 
`-u, --user string`                    | Username or UID (format: &#60;name&#124;uid&#62;[:&#60;group&#124;gid&#62;]) 
`--userns string`                      | User namespace to use 
`--uts string`                         | UTS namespace to use 
`-v, --volume list`                    | Bind mount a volume 
`--volume-driver string`               | Optional volume driver for the container 
`--volumes-from list`                  | Mount volumes from the specified container(s) 
`-w, --workdir string`                 | Working directory inside the container 



-----
### docker container diff
Inspect changes to files or directories on a container's filesystem

```bash
docker container diff CONTAINER
```


-----
### docker container exec
Run a command in a running container

```bash
docker container exec [OPTIONS] CONTAINER COMMAND [ARG...]
```

#### Options: 

Options | Description 
---------------------------- | ------------------------------------------ 
`-d, --detach`               | Detached mode: run command in the background 
`--detach-keys string`       | Override the key sequence for detaching a container 
`-e, --env list`             | Set environment variables 
`-i, --interactive`          | Keep STDIN open even if not attached 
`--privileged`               | Give extended privileges to the command 
`-t, --tty`                  | Allocate a pseudo-TTY 
`-u, --user string`          | Username or UID (format: &#60;name&#124;uid&#62;[:&#60;group&#124;gid&#62;]) 
`-w, --workdir string`       | Working directory inside the container 



-----
### docker container export
Export a container's filesystem as a tar archive

```bash
docker container export [OPTIONS] CONTAINER
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-o, --output string`   | Write to a file, instead of STDOUT 



-----
### docker container inspect
Display detailed information on one or more containers

```bash
docker container inspect [OPTIONS] CONTAINER [CONTAINER...]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --format string`   | Format the output using the given Go template 
`-s, --size`            | Display total file sizes 



-----
### docker container kill
Kill one or more running containers

```bash
docker container kill [OPTIONS] CONTAINER [CONTAINER...]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-s, --signal string`   | Signal to send to the container (default "KILL") 



-----
### docker container logs
Fetch the logs of a container

```bash
docker container logs [OPTIONS] CONTAINER
```

#### Options: 

Options | Description 
---------------------- | ------------------------------------------------ 
`--details`            | Show extra details provided to logs 
`-f, --follow`         | Follow log output 
`--since string`       | Show logs since timestamp (e.g. 2013-01-02T13:23:37) or relative (e.g. 42m for 42 minutes) 
`--tail string`        | Number of lines to show from the end of the logs (default "all") 
`-t, --timestamps`     | Show timestamps 
`--until string`       | Show logs before a timestamp (e.g. 2013-01-02T13:23:37) or relative (e.g. 42m for 42 minutes) 



-----
### docker container ls
List containers

```bash
docker container ls [OPTIONS]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-a, --all`             | Show all containers (default shows just running) 
`-f, --filter filter`   | Filter output based on conditions provided 
`--format string`       | Pretty-print containers using a Go template 
`-n, --last int`        | Show n last created containers (includes all states) (default -1) 
`-l, --latest`          | Show the latest created container (includes all states) 
`--no-trunc`            | Don't truncate output 
`-q, --quiet`           | Only display numeric IDs 
`-s, --size`            | Display total file sizes 



-----
### docker container pause
Pause all processes within one or more containers

```bash
docker container pause CONTAINER [CONTAINER...]
```


-----
### docker container port
List port mappings or a specific mapping for the container

```bash
docker container port CONTAINER [PRIVATE_PORT[/PROTO]]
```


-----
### docker container prune
Remove all stopped containers

```bash
docker container prune [OPTIONS]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`--filter filter`       | Provide filter values (e.g. 'until=&#60;timestamp&#62;') 
`-f, --force`           | Do not prompt for confirmation 



-----
### docker container rename
Rename a container

```bash
docker container rename CONTAINER NEW_NAME
```


-----
### docker container restart
Restart one or more containers

```bash
docker container restart [OPTIONS] CONTAINER [CONTAINER...]
```

#### Options: 

Options | Description 
------------------ | ---------------------------------------------------- 
`-t, --time int`   | Seconds to wait for stop before killing the container (default 10) 



-----
### docker container rm
Remove one or more containers

```bash
docker container rm [OPTIONS] CONTAINER [CONTAINER...]
```

#### Options: 

Options | Description 
----------------- | ----------------------------------------------------- 
`-f, --force`     | Force the removal of a running container (uses SIGKILL) 
`-l, --link`      | Remove the specified link 
`-v, --volumes`   | Remove the volumes associated with the container 



-----
### docker container run
Run a command in a new container

```bash
docker container run [OPTIONS] IMAGE [COMMAND] [ARG...]
```

#### Options: 

Options | Description 
-------------------------------------- | -------------------------------- 
`--add-host list`                      | Add a custom host-to-IP mapping (host:ip) 
`-a, --attach list`                    | Attach to STDIN, STDOUT or STDERR 
`--blkio-weight uint16`                | Block IO (relative weight), between 10 and 1000, or 0 to disable (default 0) 
`--blkio-weight-device list`           | Block IO weight (relative device weight) (default []) 
`--cap-add list`                       | Add Linux capabilities 
`--cap-drop list`                      | Drop Linux capabilities 
`--cgroup-parent string`               | Optional parent cgroup for the container 
`--cidfile string`                     | Write the container ID to the file 
`--cpu-period int`                     | Limit CPU CFS (Completely Fair Scheduler) period 
`--cpu-quota int`                      | Limit CPU CFS (Completely Fair Scheduler) quota 
`--cpu-rt-period int`                  | Limit CPU real-time period in microseconds 
`--cpu-rt-runtime int`                 | Limit CPU real-time runtime in microseconds 
`-c, --cpu-shares int`                 | CPU shares (relative weight) 
`--cpus decimal`                       | Number of CPUs 
`--cpuset-cpus string`                 | CPUs in which to allow execution (0-3, 0,1) 
`--cpuset-mems string`                 | MEMs in which to allow execution (0-3, 0,1) 
`-d, --detach`                         | Run container in background and print container ID 
`--detach-keys string`                 | Override the key sequence for detaching a container 
`--device list`                        | Add a host device to the container 
`--device-cgroup-rule list`            | Add a rule to the cgroup allowed devices list 
`--device-read-bps list`               | Limit read rate (bytes per second) from a device (default []) 
`--device-read-iops list`              | Limit read rate (IO per second) from a device (default []) 
`--device-write-bps list`              | Limit write rate (bytes per second) to a device (default []) 
`--device-write-iops list`             | Limit write rate (IO per second) to a device (default []) 
`--disable-content-trust`              | Skip image verification (default true) 
`--dns list`                           | Set custom DNS servers 
`--dns-option list`                    | Set DNS options 
`--dns-search list`                    | Set custom DNS search domains 
`--entrypoint string`                  | Overwrite the default ENTRYPOINT of the image 
`-e, --env list`                       | Set environment variables 
`--env-file list`                      | Read in a file of environment variables 
`--expose list`                        | Expose a port or a range of ports 
`--group-add list`                     | Add additional groups to join 
`--health-cmd string`                  | Command to run to check health 
`--health-interval duration`           | Time between running the check (ms&#124;s&#124;m&#124;h) (default 0s) 
`--health-retries int`                 | Consecutive failures needed to report unhealthy 
`--health-start-period duration`       | Start period for the container to initialize before starting health-retries countdown (ms&#124;s&#124;m&#124;h) (default 0s) 
`--health-timeout duration`            | Maximum time to allow one check to run (ms&#124;s&#124;m&#124;h) (default 0s) 
`--help`                               | Print usage 
`-h, --hostname string`                | Container host name 
`--init`                               | Run an init inside the container that forwards signals and reaps processes 
`-i, --interactive`                    | Keep STDIN open even if not attached 
`--ip string`                          | IPv4 address (e.g., 172.30.100.104) 
`--ip6 string`                         | IPv6 address (e.g., 2001:db8::33) 
`--ipc string`                         | IPC mode to use 
`--isolation string`                   | Container isolation technology 
`--kernel-memory bytes`                | Kernel memory limit 
`-l, --label list`                     | Set meta data on a container 
`--label-file list`                    | Read in a line delimited file of labels 
`--link list`                          | Add link to another container 
`--link-local-ip list`                 | Container IPv4/IPv6 link-local addresses 
`--log-driver string`                  | Logging driver for the container 
`--log-opt list`                       | Log driver options 
`--mac-address string`                 | Container MAC address (e.g., 92:d0:c6:0a:29:33) 
`-m, --memory bytes`                   | Memory limit 
`--memory-reservation bytes`           | Memory soft limit 
`--memory-swap bytes`                  | Swap limit equal to memory plus swap: '-1' to enable unlimited swap 
`--memory-swappiness int`              | Tune container memory swappiness (0 to 100) (default -1) 
`--mount mount`                        | Attach a filesystem mount to the container 
`--name string`                        | Assign a name to the container 
`--network string`                     | Connect a container to a network (default "default") 
`--network-alias list`                 | Add network-scoped alias for the container 
`--no-healthcheck`                     | Disable any container-specified HEALTHCHECK 
`--oom-kill-disable`                   | Disable OOM Killer 
`--oom-score-adj int`                  | Tune host's OOM preferences (-1000 to 1000) 
`--pid string`                         | PID namespace to use 
`--pids-limit int`                     | Tune container pids limit (set -1 for unlimited) 
`--platform string`                    | Set platform if server is multi-platform capable 
`--privileged`                         | Give extended privileges to this container 
`-p, --publish list`                   | Publish a container's port(s) to the host 
`-P, --publish-all`                    | Publish all exposed ports to random ports 
`--read-only`                          | Mount the container's root filesystem as read only 
`--restart string`                     | Restart policy to apply when a container exits (default "no") 
`--rm`                                 | Automatically remove the container when it exits 
`--runtime string`                     | Runtime to use for this container 
`--security-opt list`                  | Security Options 
`--shm-size bytes`                     | Size of /dev/shm 
`--sig-proxy`                          | Proxy received signals to the process (default true) 
`--stop-signal string`                 | Signal to stop a container (default "SIGTERM") 
`--stop-timeout int`                   | Timeout (in seconds) to stop a container 
`--storage-opt list`                   | Storage driver options for the container 
`--sysctl map`                         | Sysctl options (default map[]) 
`--tmpfs list`                         | Mount a tmpfs directory 
`-t, --tty`                            | Allocate a pseudo-TTY 
`--ulimit ulimit`                      | Ulimit options (default []) 
`-u, --user string`                    | Username or UID (format: &#60;name&#124;uid&#62;[:&#60;group&#124;gid&#62;]) 
`--userns string`                      | User namespace to use 
`--uts string`                         | UTS namespace to use 
`-v, --volume list`                    | Bind mount a volume 
`--volume-driver string`               | Optional volume driver for the container 
`--volumes-from list`                  | Mount volumes from the specified container(s) 
`-w, --workdir string`                 | Working directory inside the container 



-----
### docker container start
Start one or more stopped containers

```bash
docker container start [OPTIONS] CONTAINER [CONTAINER...]
```

#### Options: 

Options | Description 
------------------------------- | --------------------------------------- 
`-a, --attach`                  | Attach STDOUT/STDERR and forward signals 
`--checkpoint string`           | Restore from this checkpoint 
`--checkpoint-dir string`       | Use a custom checkpoint storage directory 
`--detach-keys string`          | Override the key sequence for detaching a container 
`-i, --interactive`             | Attach container's STDIN 



-----
### docker container stats
Display a live stream of container(s) resource usage statistics

```bash
docker container stats [OPTIONS] [CONTAINER...]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-a, --all`             | Show all containers (default shows just running) 
`--format string`       | Pretty-print images using a Go template 
`--no-stream`           | Disable streaming stats and only pull the first result 
`--no-trunc`            | Do not truncate output 



-----
### docker container stop
Stop one or more running containers

```bash
docker container stop [OPTIONS] CONTAINER [CONTAINER...]
```

#### Options: 

Options | Description 
------------------ | ---------------------------------------------------- 
`-t, --time int`   | Seconds to wait for stop before killing it (default 10) 



-----
### docker container top
Display the running processes of a container

```bash
docker container top CONTAINER [ps OPTIONS]
```


-----
### docker container unpause
Unpause all processes within one or more containers

```bash
docker container unpause CONTAINER [CONTAINER...]
```


-----
### docker container update
Update configuration of one or more containers

```bash
docker container update [OPTIONS] CONTAINER [CONTAINER...]
```

#### Options: 

Options | Description 
---------------------------------- | ------------------------------------ 
`--blkio-weight uint16`            | Block IO (relative weight), between 10 and 1000, or 0 to disable (default 0) 
`--cpu-period int`                 | Limit CPU CFS (Completely Fair Scheduler) period 
`--cpu-quota int`                  | Limit CPU CFS (Completely Fair Scheduler) quota 
`--cpu-rt-period int`              | Limit the CPU real-time period in microseconds 
`--cpu-rt-runtime int`             | Limit the CPU real-time runtime in microseconds 
`-c, --cpu-shares int`             | CPU shares (relative weight) 
`--cpus decimal`                   | Number of CPUs 
`--cpuset-cpus string`             | CPUs in which to allow execution (0-3, 0,1) 
`--cpuset-mems string`             | MEMs in which to allow execution (0-3, 0,1) 
`--kernel-memory bytes`            | Kernel memory limit 
`-m, --memory bytes`               | Memory limit 
`--memory-reservation bytes`       | Memory soft limit 
`--memory-swap bytes`              | Swap limit equal to memory plus swap: '-1' to enable unlimited swap 
`--restart string`                 | Restart policy to apply when a container exits 



-----
### docker container wait
Block until one or more containers stop, then print their exit codes

```bash
docker container wait CONTAINER [CONTAINER...]
```


-----
## docker image
Manage images

```bash
docker image COMMAND
```

### Commands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 `docker image build`      | Build an image from a Dockerfile 
 `docker image history`    | Show the history of an image 
 `docker image import`     | Import the contents from a tarball to create a filesystem image 
 `docker image inspect`    | Display detailed information on one or more images 
 `docker image load`       | Load an image from a tar archive or STDIN 
 `docker image ls`         | List images 
 `docker image prune`      | Remove unused images 
 `docker image pull`       | Pull an image or a repository from a registry 
 `docker image push`       | Push an image or a repository to a registry 
 `docker image rm`         | Remove one or more images 
 `docker image save`       | Save one or more images to a tar archive (streamed to STDOUT by default) 
 `docker image tag`        | Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE 


### docker image build
Build an image from a Dockerfile

```bash
docker image build [OPTIONS] PATH | URL | -
```

#### Options: 

Options | Description 
------------------------------- | --------------------------------------- 
`--add-host list`               | Add a custom host-to-IP mapping (host:ip) 
`--build-arg list`              | Set build-time variables 
`--cache-from strings`          | Images to consider as cache sources 
`--cgroup-parent string`        | Optional parent cgroup for the container 
`--compress`                    | Compress the build context using gzip 
`--cpu-period int`              | Limit the CPU CFS (Completely Fair Scheduler) period 
`--cpu-quota int`               | Limit the CPU CFS (Completely Fair Scheduler) quota 
`-c, --cpu-shares int`          | CPU shares (relative weight) 
`--cpuset-cpus string`          | CPUs in which to allow execution (0-3, 0,1) 
`--cpuset-mems string`          | MEMs in which to allow execution (0-3, 0,1) 
`--disable-content-trust`       | Skip image verification (default true) 
`-f, --file string`             | Name of the Dockerfile (Default is 'PATH/Dockerfile') 
`--force-rm`                    | Always remove intermediate containers 
`--iidfile string`              | Write the image ID to the file 
`--isolation string`            | Container isolation technology 
`--label list`                  | Set metadata for an image 
`-m, --memory bytes`            | Memory limit 
`--memory-swap bytes`           | Swap limit equal to memory plus swap: '-1' to enable unlimited swap 
`--network string`              | Set the networking mode for the RUN instructions during build (default "default") 
`--no-cache`                    | Do not use cache when building the image 
`--platform string`             | Set platform if server is multi-platform capable 
`--pull`                        | Always attempt to pull a newer version of the image 
`-q, --quiet`                   | Suppress the build output and print image ID on success 
`--rm`                          | Remove intermediate containers after a successful build (default true) 
`--security-opt strings`        | Security options 
`--shm-size bytes`              | Size of /dev/shm 
`--squash`                      | Squash newly built layers into a single new layer 
`--stream`                      | Stream attaches to server to negotiate build context 
`-t, --tag list`                | Name and optionally a tag in the 'name:tag' format 
`--target string`               | Set the target build stage to build. 
`--ulimit ulimit`               | Ulimit options (default []) 



-----
### docker image history
Show the history of an image

```bash
docker image history [OPTIONS] IMAGE
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`--format string`       | Pretty-print images using a Go template 
`-H, --human`           | Print sizes and dates in human readable format (default true) 
`--no-trunc`            | Don't truncate output 
`-q, --quiet`           | Only show numeric IDs 



-----
### docker image import
Import the contents from a tarball to create a filesystem image

```bash
docker image import [OPTIONS] file|URL|- [REPOSITORY[:TAG]]
```

#### Options: 

Options | Description 
------------------------ | ---------------------------------------------- 
`-c, --change list`      | Apply Dockerfile instruction to the created image 
`-m, --message string`   | Set commit message for imported image 



-----
### docker image inspect
Display detailed information on one or more images

```bash
docker image inspect [OPTIONS] IMAGE [IMAGE...]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --format string`   | Format the output using the given Go template 



-----
### docker image load
Load an image from a tar archive or STDIN

```bash
docker image load [OPTIONS]
```

#### Options: 

Options | Description 
---------------------- | ------------------------------------------------ 
`-i, --input string`   | Read from tar archive file, instead of STDIN 
`-q, --quiet`          | Suppress the load output 



-----
### docker image ls
List images

```bash
docker image ls [OPTIONS] [REPOSITORY[:TAG]]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-a, --all`             | Show all images (default hides intermediate images) 
`--digests`             | Show digests 
`-f, --filter filter`   | Filter output based on conditions provided 
`--format string`       | Pretty-print images using a Go template 
`--no-trunc`            | Don't truncate output 
`-q, --quiet`           | Only show numeric IDs 



-----
### docker image prune
Remove unused images

```bash
docker image prune [OPTIONS]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-a, --all`             | Remove all unused images, not just dangling ones 
`--filter filter`       | Provide filter values (e.g. 'until=&#60;timestamp&#62;') 
`-f, --force`           | Do not prompt for confirmation 



-----
### docker image pull
Pull an image or a repository from a registry

```bash
docker image pull [OPTIONS] NAME[:TAG|@DIGEST]
```

#### Options: 

Options | Description 
------------------------------- | --------------------------------------- 
`-a, --all-tags`                | Download all tagged images in the repository 
`--disable-content-trust`       | Skip image verification (default true) 
`--platform string`             | Set platform if server is multi-platform capable 



-----
### docker image push
Push an image or a repository to a registry

```bash
docker image push [OPTIONS] NAME[:TAG]
```

#### Options: 

Options | Description 
------------------------------- | --------------------------------------- 
`--disable-content-trust`       | Skip image signing (default true) 



-----
### docker image rm
Remove one or more images

```bash
docker image rm [OPTIONS] IMAGE [IMAGE...]
```

#### Options: 

Options | Description 
------------------ | ---------------------------------------------------- 
`-f, --force`      | Force removal of the image 
`--no-prune`       | Do not delete untagged parents 



-----
### docker image save
Save one or more images to a tar archive (streamed to STDOUT by default)

```bash
docker image save [OPTIONS] IMAGE [IMAGE...]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-o, --output string`   | Write to a file, instead of STDOUT 



-----
### docker image tag
Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE

```bash
docker image tag SOURCE_IMAGE[:TAG] TARGET_IMAGE[:TAG]
```


-----
## docker network
Manage networks

```bash
docker network COMMAND
```

### Commands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 `docker network connect`  | Connect a container to a network 
 `docker network create`   | Create a network 
 `docker network disconnect` | Disconnect a container from a network 
 `docker network inspect`  | Display detailed information on one or more networks 
 `docker network ls`       | List networks 
 `docker network prune`    | Remove all unused networks 
 `docker network rm`       | Remove one or more networks 


### docker network connect
Connect a container to a network

```bash
docker network connect [OPTIONS] NETWORK CONTAINER
```

#### Options: 

Options | Description 
------------------------------- | --------------------------------------- 
`--alias strings`               | Add network-scoped alias for the container 
`--ip string`                   | IPv4 address (e.g., 172.30.100.104) 
`--ip6 string`                  | IPv6 address (e.g., 2001:db8::33) 
`--link list`                   | Add link to another container 
`--link-local-ip strings`       | Add a link-local address for the container 



-----
### docker network create
Create a network

```bash
docker network create [OPTIONS] NETWORK
```

#### Options: 

Options | Description 
---------------------------- | ------------------------------------------ 
`--attachable`               | Enable manual container attachment 
`--aux-address map`          | Auxiliary IPv4 or IPv6 addresses used by Network driver (default map[]) 
`--config-from string`       | The network from which copying the configuration 
`--config-only`              | Create a configuration only network 
`-d, --driver string`        | Driver to manage the Network (default "bridge") 
`--gateway strings`          | IPv4 or IPv6 Gateway for the master subnet 
`--ingress`                  | Create swarm routing-mesh network 
`--internal`                 | Restrict external access to the network 
`--ip-range strings`         | Allocate container ip from a sub-range 
`--ipam-driver string`       | IP Address Management Driver (default "default") 
`--ipam-opt map`             | Set IPAM driver specific options (default map[]) 
`--ipv6`                     | Enable IPv6 networking 
`--label list`               | Set metadata on a network 
`-o, --opt map`              | Set driver specific options (default map[]) 
`--scope string`             | Control the network's scope 
`--subnet strings`           | Subnet in CIDR format that represents a network segment 



-----
### docker network disconnect
Disconnect a container from a network

```bash
docker network disconnect [OPTIONS] NETWORK CONTAINER
```

#### Options: 

Options | Description 
--------------- | ------------------------------------------------------- 
`-f, --force`   | Force the container to disconnect from a network 



-----
### docker network inspect
Display detailed information on one or more networks

```bash
docker network inspect [OPTIONS] NETWORK [NETWORK...]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --format string`   | Format the output using the given Go template 
`-v, --verbose`         | Verbose output for diagnostics 



-----
### docker network ls
List networks

```bash
docker network ls [OPTIONS]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --filter filter`   | Provide filter values (e.g. 'driver=bridge') 
`--format string`       | Pretty-print networks using a Go template 
`--no-trunc`            | Do not truncate the output 
`-q, --quiet`           | Only display network IDs 



-----
### docker network prune
Remove all unused networks

```bash
docker network prune [OPTIONS]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`--filter filter`       | Provide filter values (e.g. 'until=&#60;timestamp&#62;') 
`-f, --force`           | Do not prompt for confirmation 



-----
### docker network rm
Remove one or more networks

```bash
docker network rm NETWORK [NETWORK...]
```


-----
## docker node
Manage Swarm nodes

```bash
docker node COMMAND
```

### Commands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 `docker node demote`      | Demote one or more nodes from manager in the swarm 
 `docker node inspect`     | Display detailed information on one or more nodes 
 `docker node ls`          | List nodes in the swarm 
 `docker node promote`     | Promote one or more nodes to manager in the swarm 
 `docker node ps`          | List tasks running on one or more nodes, defaults to current node 
 `docker node rm`          | Remove one or more nodes from the swarm 
 `docker node update`      | Update a node 


### docker node demote
Demote one or more nodes from manager in the swarm

```bash
docker node demote NODE [NODE...]
```


-----
### docker node inspect
Display detailed information on one or more nodes

```bash
docker node inspect [OPTIONS] self|NODE [NODE...]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --format string`   | Format the output using the given Go template 
`--pretty`              | Print the information in a human friendly format 



-----
### docker node ls
List nodes in the swarm

```bash
docker node ls [OPTIONS]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --filter filter`   | Filter output based on conditions provided 
`--format string`       | Pretty-print nodes using a Go template 
`-q, --quiet`           | Only display IDs 



-----
### docker node promote
Promote one or more nodes to manager in the swarm

```bash
docker node promote NODE [NODE...]
```


-----
### docker node ps
List tasks running on one or more nodes, defaults to current node

```bash
docker node ps [OPTIONS] [NODE...]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --filter filter`   | Filter output based on conditions provided 
`--format string`       | Pretty-print tasks using a Go template 
`--no-resolve`          | Do not map IDs to Names 
`--no-trunc`            | Do not truncate output 
`-q, --quiet`           | Only display task IDs 



-----
### docker node rm
Remove one or more nodes from the swarm

```bash
docker node rm [OPTIONS] NODE [NODE...]
```

#### Options: 

Options | Description 
--------------- | ------------------------------------------------------- 
`-f, --force`   | Force remove a node from the swarm 



-----
### docker node update
Update a node

```bash
docker node update [OPTIONS] NODE
```

#### Options: 

Options | Description 
----------------------------- | ----------------------------------------- 
`--availability string`       | Availability of the node ("active"&#124;"pause"&#124;"drain") 
`--label-add list`            | Add or update a node label (key=value) 
`--label-rm list`             | Remove a node label if exists 
`--role string`               | Role of the node ("worker"&#124;"manager") 



-----
## docker plugin
Manage plugins

```bash
docker plugin COMMAND
```

### Commands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 `docker plugin create`    | Create a plugin from a rootfs and configuration. Plugin data directory must contain config.json and rootfs directory. 
 `docker plugin disable`   | Disable a plugin 
 `docker plugin enable`    | Enable a plugin 
 `docker plugin inspect`   | Display detailed information on one or more plugins 
 `docker plugin install`   | Install a plugin 
 `docker plugin ls`        | List plugins 
 `docker plugin push`      | Push a plugin to a registry 
 `docker plugin rm`        | Remove one or more plugins 
 `docker plugin set`       | Change settings for a plugin 
 `docker plugin upgrade`   | Upgrade an existing plugin 


### docker plugin create
Create a plugin from a rootfs and configuration. Plugin data directory must contain config.json and rootfs directory.

```bash
docker plugin create [OPTIONS] PLUGIN PLUGIN-DATA-DIR
```

#### Options: 

Options | Description 
------------------ | ---------------------------------------------------- 
`--compress`       | Compress the context using gzip 



-----
### docker plugin disable
Disable a plugin

```bash
docker plugin disable [OPTIONS] PLUGIN
```

#### Options: 

Options | Description 
--------------- | ------------------------------------------------------- 
`-f, --force`   | Force the disable of an active plugin 



-----
### docker plugin enable
Enable a plugin

```bash
docker plugin enable [OPTIONS] PLUGIN
```

#### Options: 

Options | Description 
--------------------- | ------------------------------------------------- 
`--timeout int`       | HTTP client timeout (in seconds) (default 30) 



-----
### docker plugin inspect
Display detailed information on one or more plugins

```bash
docker plugin inspect [OPTIONS] PLUGIN [PLUGIN...]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --format string`   | Format the output using the given Go template 



-----
### docker plugin install
Install a plugin

```bash
docker plugin install [OPTIONS] PLUGIN [KEY=VALUE...]
```

#### Options: 

Options | Description 
------------------------------- | --------------------------------------- 
`--alias string`                | Local name for plugin 
`--disable`                     | Do not enable the plugin on install 
`--disable-content-trust`       | Skip image verification (default true) 
`--grant-all-permissions`       | Grant all permissions necessary to run the plugin 



-----
### docker plugin ls
List plugins

```bash
docker plugin ls [OPTIONS]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --filter filter`   | Provide filter values (e.g. 'enabled=true') 
`--format string`       | Pretty-print plugins using a Go template 
`--no-trunc`            | Don't truncate output 
`-q, --quiet`           | Only display plugin IDs 



-----
### docker plugin push
Push a plugin to a registry

```bash
docker plugin push [OPTIONS] PLUGIN[:TAG]
```

#### Options: 

Options | Description 
------------------------------- | --------------------------------------- 
`--disable-content-trust`       | Skip image signing (default true) 



-----
### docker plugin rm
Remove one or more plugins

```bash
docker plugin rm [OPTIONS] PLUGIN [PLUGIN...]
```

#### Options: 

Options | Description 
--------------- | ------------------------------------------------------- 
`-f, --force`   | Force the removal of an active plugin 



-----
### docker plugin set
Change settings for a plugin

```bash
docker plugin set PLUGIN KEY=VALUE [KEY=VALUE...]
```


-----
### docker plugin upgrade
Upgrade an existing plugin

```bash
docker plugin upgrade [OPTIONS] PLUGIN [REMOTE]
```

#### Options: 

Options | Description 
------------------------------- | --------------------------------------- 
`--disable-content-trust`       | Skip image verification (default true) 
`--grant-all-permissions`       | Grant all permissions necessary to run the plugin 
`--skip-remote-check`           | Do not check if specified remote plugin matches existing plugin image 



-----
## docker secret
Manage Docker secrets

```bash
docker secret COMMAND
```

### Commands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 `docker secret create`    | Create a secret from a file or STDIN as content 
 `docker secret inspect`   | Display detailed information on one or more secrets 
 `docker secret ls`        | List secrets 
 `docker secret rm`        | Remove one or more secrets 


### docker secret create
Create a secret from a file or STDIN as content

```bash
docker secret create [OPTIONS] SECRET [file|-]
```

#### Options: 

Options | Description 
-------------------------------- | -------------------------------------- 
`-d, --driver string`            | Secret driver 
`-l, --label list`               | Secret labels 
`--template-driver string`       | Template driver 



-----
### docker secret inspect
Display detailed information on one or more secrets

```bash
docker secret inspect [OPTIONS] SECRET [SECRET...]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --format string`   | Format the output using the given Go template 
`--pretty`              | Print the information in a human friendly format 



-----
### docker secret ls
List secrets

```bash
docker secret ls [OPTIONS]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --filter filter`   | Filter output based on conditions provided 
`--format string`       | Pretty-print secrets using a Go template 
`-q, --quiet`           | Only display IDs 



-----
### docker secret rm
Remove one or more secrets

```bash
docker secret rm SECRET [SECRET...]
```


-----
## docker service
Manage services

```bash
docker service COMMAND
```

### Commands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 `docker service create`   | Create a new service 
 `docker service inspect`  | Display detailed information on one or more services 
 `docker service logs`     | Fetch the logs of a service or task 
 `docker service ls`       | List services 
 `docker service ps`       | List the tasks of one or more services 
 `docker service rm`       | Remove one or more services 
 `docker service rollback` | Revert changes to a service's configuration 
 `docker service scale`    | Scale one or multiple replicated services 
 `docker service update`   | Update a service 


### docker service create
Create a new service

```bash
docker service create [OPTIONS] IMAGE [COMMAND] [ARG...]
```

#### Options: 

Options | Description 
------------------------------------------ | ---------------------------- 
`--config config`                          | Specify configurations to expose to the service 
`--constraint list`                        | Placement constraints 
`--container-label list`                   | Container labels 
`--credential-spec credential-spec`        | Credential spec for managed service account (Windows only) 
`-d, --detach`                             | Exit immediately instead of waiting for the service to converge 
`--dns list`                               | Set custom DNS servers 
`--dns-option list`                        | Set DNS options 
`--dns-search list`                        | Set custom DNS search domains 
`--endpoint-mode string`                   | Endpoint mode (vip or dnsrr) (default "vip") 
`--entrypoint command`                     | Overwrite the default ENTRYPOINT of the image 
`-e, --env list`                           | Set environment variables 
`--env-file list`                          | Read in a file of environment variables 
`--generic-resource list`                  | User defined resources 
`--group list`                             | Set one or more supplementary user groups for the container 
`--health-cmd string`                      | Command to run to check health 
`--health-interval duration`               | Time between running the check (ms&#124;s&#124;m&#124;h) 
`--health-retries int`                     | Consecutive failures needed to report unhealthy 
`--health-start-period duration`           | Start period for the container to initialize before counting retries towards unstable (ms&#124;s&#124;m&#124;h) 
`--health-timeout duration`                | Maximum time to allow one check to run (ms&#124;s&#124;m&#124;h) 
`--host list`                              | Set one or more custom host-to-IP mappings (host:ip) 
`--hostname string`                        | Container hostname 
`--isolation string`                       | Service container isolation mode 
`-l, --label list`                         | Service labels 
`--limit-cpu decimal`                      | Limit CPUs 
`--limit-memory bytes`                     | Limit Memory 
`--log-driver string`                      | Logging driver for service 
`--log-opt list`                           | Logging driver options 
`--mode string`                            | Service mode (replicated or global) (default "replicated") 
`--mount mount`                            | Attach a filesystem mount to the service 
`--name string`                            | Service name 
`--network network`                        | Network attachments 
`--no-healthcheck`                         | Disable any container-specified HEALTHCHECK 
`--no-resolve-image`                       | Do not query the registry to resolve image digest and supported platforms 
`--placement-pref pref`                    | Add a placement preference 
`-p, --publish port`                       | Publish a port as a node port 
`-q, --quiet`                              | Suppress progress output 
`--read-only`                              | Mount the container's root filesystem as read only 
`--replicas uint`                          | Number of tasks 
`--reserve-cpu decimal`                    | Reserve CPUs 
`--reserve-memory bytes`                   | Reserve Memory 
`--restart-condition string`               | Restart when condition is met ("none"&#124;"on-failure"&#124;"any") (default "any") 
`--restart-delay duration`                 | Delay between restart attempts (ns&#124;us&#124;ms&#124;s&#124;m&#124;h) (default 5s) 
`--restart-max-attempts uint`              | Maximum number of restarts before giving up 
`--restart-window duration`                | Window used to evaluate the restart policy (ns&#124;us&#124;ms&#124;s&#124;m&#124;h) 
`--rollback-delay duration`                | Delay between task rollbacks (ns&#124;us&#124;ms&#124;s&#124;m&#124;h) (default 0s) 
`--rollback-failure-action string`         | Action on rollback failure ("pause"&#124;"continue") (default "pause") 
`--rollback-max-failure-ratio float`       | Failure rate to tolerate during a rollback (default 0) 
`--rollback-monitor duration`              | Duration after each task rollback to monitor for failure (ns&#124;us&#124;ms&#124;s&#124;m&#124;h) (default 5s) 
`--rollback-order string`                  | Rollback order ("start-first"&#124;"stop-first") (default "stop-first") 
`--rollback-parallelism uint`              | Maximum number of tasks rolled back simultaneously (0 to roll back all at once) (default 1) 
`--secret secret`                          | Specify secrets to expose to the service 
`--stop-grace-period duration`             | Time to wait before force killing a container (ns&#124;us&#124;ms&#124;s&#124;m&#124;h) (default 10s) 
`--stop-signal string`                     | Signal to stop the container 
`-t, --tty`                                | Allocate a pseudo-TTY 
`--update-delay duration`                  | Delay between updates (ns&#124;us&#124;ms&#124;s&#124;m&#124;h) (default 0s) 
`--update-failure-action string`           | Action on update failure ("pause"&#124;"continue"&#124;"rollback") (default "pause") 
`--update-max-failure-ratio float`         | Failure rate to tolerate during an update (default 0) 
`--update-monitor duration`                | Duration after each task update to monitor for failure (ns&#124;us&#124;ms&#124;s&#124;m&#124;h) (default 5s) 
`--update-order string`                    | Update order ("start-first"&#124;"stop-first") (default "stop-first") 
`--update-parallelism uint`                | Maximum number of tasks updated simultaneously (0 to update all at once) (default 1) 
`-u, --user string`                        | Username or UID (format: &#60;name&#124;uid&#62;[:&#60;group&#124;gid&#62;]) 
`--with-registry-auth`                     | Send registry authentication details to swarm agents 
`-w, --workdir string`                     | Working directory inside the container 



-----
### docker service inspect
Display detailed information on one or more services

```bash
docker service inspect [OPTIONS] SERVICE [SERVICE...]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --format string`   | Format the output using the given Go template 
`--pretty`              | Print the information in a human friendly format 



-----
### docker service logs
Fetch the logs of a service or task

```bash
docker service logs [OPTIONS] SERVICE|TASK
```

#### Options: 

Options | Description 
---------------------- | ------------------------------------------------ 
`--details`            | Show extra details provided to logs 
`-f, --follow`         | Follow log output 
`--no-resolve`         | Do not map IDs to Names in output 
`--no-task-ids`        | Do not include task IDs in output 
`--no-trunc`           | Do not truncate output 
`--raw`                | Do not neatly format logs 
`--since string`       | Show logs since timestamp (e.g. 2013-01-02T13:23:37) or relative (e.g. 42m for 42 minutes) 
`--tail string`        | Number of lines to show from the end of the logs (default "all") 
`-t, --timestamps`     | Show timestamps 



-----
### docker service ls
List services

```bash
docker service ls [OPTIONS]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --filter filter`   | Filter output based on conditions provided 
`--format string`       | Pretty-print services using a Go template 
`-q, --quiet`           | Only display IDs 



-----
### docker service ps
List the tasks of one or more services

```bash
docker service ps [OPTIONS] SERVICE [SERVICE...]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --filter filter`   | Filter output based on conditions provided 
`--format string`       | Pretty-print tasks using a Go template 
`--no-resolve`          | Do not map IDs to Names 
`--no-trunc`            | Do not truncate output 
`-q, --quiet`           | Only display task IDs 



-----
### docker service rm
Remove one or more services

```bash
docker service rm SERVICE [SERVICE...]
```


-----
### docker service rollback
Revert changes to a service's configuration

```bash
docker service rollback [OPTIONS] SERVICE
```

#### Options: 

Options | Description 
---------------- | ------------------------------------------------------ 
`-d, --detach`   | Exit immediately instead of waiting for the service to converge 
`-q, --quiet`    | Suppress progress output 



-----
### docker service scale
Scale one or multiple replicated services

```bash
docker service scale SERVICE=REPLICAS [SERVICE=REPLICAS...]
```

#### Options: 

Options | Description 
---------------- | ------------------------------------------------------ 
`-d, --detach`   | Exit immediately instead of waiting for the service to converge 



-----
### docker service update
Update a service

```bash
docker service update [OPTIONS] SERVICE
```

#### Options: 

Options | Description 
------------------------------------------ | ---------------------------- 
`--args command`                           | Service command args 
`--config-add config`                      | Add or update a config file on a service 
`--config-rm list`                         | Remove a configuration file 
`--constraint-add list`                    | Add or update a placement constraint 
`--constraint-rm list`                     | Remove a constraint 
`--container-label-add list`               | Add or update a container label 
`--container-label-rm list`                | Remove a container label by its key 
`--credential-spec credential-spec`        | Credential spec for managed service account (Windows only) 
`-d, --detach`                             | Exit immediately instead of waiting for the service to converge 
`--dns-add list`                           | Add or update a custom DNS server 
`--dns-option-add list`                    | Add or update a DNS option 
`--dns-option-rm list`                     | Remove a DNS option 
`--dns-rm list`                            | Remove a custom DNS server 
`--dns-search-add list`                    | Add or update a custom DNS search domain 
`--dns-search-rm list`                     | Remove a DNS search domain 
`--endpoint-mode string`                   | Endpoint mode (vip or dnsrr) 
`--entrypoint command`                     | Overwrite the default ENTRYPOINT of the image 
`--env-add list`                           | Add or update an environment variable 
`--env-rm list`                            | Remove an environment variable 
`--force`                                  | Force update even if no changes require it 
`--generic-resource-add list`              | Add a Generic resource 
`--generic-resource-rm list`               | Remove a Generic resource 
`--group-add list`                         | Add an additional supplementary user group to the container 
`--group-rm list`                          | Remove a previously added supplementary user group from the container 
`--health-cmd string`                      | Command to run to check health 
`--health-interval duration`               | Time between running the check (ms&#124;s&#124;m&#124;h) 
`--health-retries int`                     | Consecutive failures needed to report unhealthy 
`--health-start-period duration`           | Start period for the container to initialize before counting retries towards unstable (ms&#124;s&#124;m&#124;h) 
`--health-timeout duration`                | Maximum time to allow one check to run (ms&#124;s&#124;m&#124;h) 
`--host-add list`                          | Add a custom host-to-IP mapping (host:ip) 
`--host-rm list`                           | Remove a custom host-to-IP mapping (host:ip) 
`--hostname string`                        | Container hostname 
`--image string`                           | Service image tag 
`--isolation string`                       | Service container isolation mode 
`--label-add list`                         | Add or update a service label 
`--label-rm list`                          | Remove a label by its key 
`--limit-cpu decimal`                      | Limit CPUs 
`--limit-memory bytes`                     | Limit Memory 
`--log-driver string`                      | Logging driver for service 
`--log-opt list`                           | Logging driver options 
`--mount-add mount`                        | Add or update a mount on a service 
`--mount-rm list`                          | Remove a mount by its target path 
`--network-add network`                    | Add a network 
`--network-rm list`                        | Remove a network 
`--no-healthcheck`                         | Disable any container-specified HEALTHCHECK 
`--no-resolve-image`                       | Do not query the registry to resolve image digest and supported platforms 
`--placement-pref-add pref`                | Add a placement preference 
`--placement-pref-rm pref`                 | Remove a placement preference 
`--publish-add port`                       | Add or update a published port 
`--publish-rm port`                        | Remove a published port by its target port 
`-q, --quiet`                              | Suppress progress output 
`--read-only`                              | Mount the container's root filesystem as read only 
`--replicas uint`                          | Number of tasks 
`--reserve-cpu decimal`                    | Reserve CPUs 
`--reserve-memory bytes`                   | Reserve Memory 
`--restart-condition string`               | Restart when condition is met ("none"&#124;"on-failure"&#124;"any") 
`--restart-delay duration`                 | Delay between restart attempts (ns&#124;us&#124;ms&#124;s&#124;m&#124;h) 
`--restart-max-attempts uint`              | Maximum number of restarts before giving up 
`--restart-window duration`                | Window used to evaluate the restart policy (ns&#124;us&#124;ms&#124;s&#124;m&#124;h) 
`--rollback`                               | Rollback to previous specification 
`--rollback-delay duration`                | Delay between task rollbacks (ns&#124;us&#124;ms&#124;s&#124;m&#124;h) 
`--rollback-failure-action string`         | Action on rollback failure ("pause"&#124;"continue") 
`--rollback-max-failure-ratio float`       | Failure rate to tolerate during a rollback 
`--rollback-monitor duration`              | Duration after each task rollback to monitor for failure (ns&#124;us&#124;ms&#124;s&#124;m&#124;h) 
`--rollback-order string`                  | Rollback order ("start-first"&#124;"stop-first") 
`--rollback-parallelism uint`              | Maximum number of tasks rolled back simultaneously (0 to roll back all at once) 
`--secret-add secret`                      | Add or update a secret on a service 
`--secret-rm list`                         | Remove a secret 
`--stop-grace-period duration`             | Time to wait before force killing a container (ns&#124;us&#124;ms&#124;s&#124;m&#124;h) 
`--stop-signal string`                     | Signal to stop the container 
`-t, --tty`                                | Allocate a pseudo-TTY 
`--update-delay duration`                  | Delay between updates (ns&#124;us&#124;ms&#124;s&#124;m&#124;h) 
`--update-failure-action string`           | Action on update failure ("pause"&#124;"continue"&#124;"rollback") 
`--update-max-failure-ratio float`         | Failure rate to tolerate during an update 
`--update-monitor duration`                | Duration after each task update to monitor for failure (ns&#124;us&#124;ms&#124;s&#124;m&#124;h) 
`--update-order string`                    | Update order ("start-first"&#124;"stop-first") 
`--update-parallelism uint`                | Maximum number of tasks updated simultaneously (0 to update all at once) 
`-u, --user string`                        | Username or UID (format: &#60;name&#124;uid&#62;[:&#60;group&#124;gid&#62;]) 
`--with-registry-auth`                     | Send registry authentication details to swarm agents 
`-w, --workdir string`                     | Working directory inside the container 



-----
## docker swarm
Manage Swarm

```bash
docker swarm COMMAND
```

### Commands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 `docker swarm ca`         | Display and rotate the root CA 
 `docker swarm init`       | Initialize a swarm 
 `docker swarm join`       | Join a swarm as a node and/or manager 
 `docker swarm join-token` | Manage join tokens 
 `docker swarm leave`      | Leave the swarm 
 `docker swarm unlock`     | Unlock swarm 
 `docker swarm unlock-key` | Manage the unlock key 
 `docker swarm update`     | Update the swarm 


### docker swarm ca
Display and rotate the root CA

```bash
docker swarm ca [OPTIONS]
```

#### Options: 

Options | Description 
--------------------------------- | ------------------------------------- 
`--ca-cert pem-file`              | Path to the PEM-formatted root CA certificate to use for the new cluster 
`--ca-key pem-file`               | Path to the PEM-formatted root CA key to use for the new cluster 
`--cert-expiry duration`          | Validity period for node certificates (ns&#124;us&#124;ms&#124;s&#124;m&#124;h) (default 2160h0m0s) 
`-d, --detach`                    | Exit immediately instead of waiting for the root rotation to converge 
`--external-ca external-ca`       | Specifications of one or more certificate signing endpoints 
`-q, --quiet`                     | Suppress progress output 
`--rotate`                        | Rotate the swarm CA - if no certificate or key are provided, new ones will be generated 



-----
### docker swarm init
Initialize a swarm

```bash
docker swarm init [OPTIONS]
```

#### Options: 

Options | Description 
--------------------------------------- | ------------------------------- 
`--advertise-addr string`               | Advertised address (format: &#60;ip&#124;interface&#62;[:port]) 
`--autolock`                            | Enable manager autolocking (requiring an unlock key to start a stopped manager) 
`--availability string`                 | Availability of the node ("active"&#124;"pause"&#124;"drain") (default "active") 
`--cert-expiry duration`                | Validity period for node certificates (ns&#124;us&#124;ms&#124;s&#124;m&#124;h) (default 2160h0m0s) 
`--data-path-addr string`               | Address or interface to use for data path traffic (format: &#60;ip&#124;interface&#62;) 
`--dispatcher-heartbeat duration`       | Dispatcher heartbeat period (ns&#124;us&#124;ms&#124;s&#124;m&#124;h) (default 5s) 
`--external-ca external-ca`             | Specifications of one or more certificate signing endpoints 
`--force-new-cluster`                   | Force create a new cluster from current state 
`--listen-addr node-addr`               | Listen address (format: &#60;ip&#124;interface&#62;[:port]) (default 0.0.0.0:2377) 
`--max-snapshots uint`                  | Number of additional Raft snapshots to retain 
`--snapshot-interval uint`              | Number of log entries between Raft snapshots (default 10000) 
`--task-history-limit int`              | Task history retention limit (default 5) 



-----
### docker swarm join
Join a swarm as a node and/or manager

```bash
docker swarm join [OPTIONS] HOST:PORT
```

#### Options: 

Options | Description 
------------------------------- | --------------------------------------- 
`--advertise-addr string`       | Advertised address (format: &#60;ip&#124;interface&#62;[:port]) 
`--availability string`         | Availability of the node ("active"&#124;"pause"&#124;"drain") (default "active") 
`--data-path-addr string`       | Address or interface to use for data path traffic (format: &#60;ip&#124;interface&#62;) 
`--listen-addr node-addr`       | Listen address (format: &#60;ip&#124;interface&#62;[:port]) (default 0.0.0.0:2377) 
`--token string`                | Token for entry into the swarm 



-----
### docker swarm join-token
Manage join tokens

```bash
docker swarm join-token [OPTIONS] (worker|manager)
```

#### Options: 

Options | Description 
---------------- | ------------------------------------------------------ 
`-q, --quiet`    | Only display token 
`--rotate`       | Rotate join token 



-----
### docker swarm leave
Leave the swarm

```bash
docker swarm leave [OPTIONS]
```

#### Options: 

Options | Description 
--------------- | ------------------------------------------------------- 
`-f, --force`   | Force this node to leave the swarm, ignoring warnings 



-----
### docker swarm unlock
Unlock swarm

```bash
docker swarm unlock
```


-----
### docker swarm unlock-key
Manage the unlock key

```bash
docker swarm unlock-key [OPTIONS]
```

#### Options: 

Options | Description 
---------------- | ------------------------------------------------------ 
`-q, --quiet`    | Only display token 
`--rotate`       | Rotate unlock key 



-----
### docker swarm update
Update the swarm

```bash
docker swarm update [OPTIONS]
```

#### Options: 

Options | Description 
--------------------------------------- | ------------------------------- 
`--autolock`                            | Change manager autolocking setting (true&#124;false) 
`--cert-expiry duration`                | Validity period for node certificates (ns&#124;us&#124;ms&#124;s&#124;m&#124;h) (default 2160h0m0s) 
`--dispatcher-heartbeat duration`       | Dispatcher heartbeat period (ns&#124;us&#124;ms&#124;s&#124;m&#124;h) (default 5s) 
`--external-ca external-ca`             | Specifications of one or more certificate signing endpoints 
`--max-snapshots uint`                  | Number of additional Raft snapshots to retain 
`--snapshot-interval uint`              | Number of log entries between Raft snapshots (default 10000) 
`--task-history-limit int`              | Task history retention limit (default 5) 



-----
## docker system
Manage Docker

```bash
docker system COMMAND
```

### Commands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 `docker system df`        | Show docker disk usage 
 `docker system events`    | Get real time events from the server 
 `docker system info`      | Display system-wide information 
 `docker system prune`     | Remove unused data 


### docker system df
Show docker disk usage

```bash
docker system df [OPTIONS]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`--format string`       | Pretty-print images using a Go template 
`-v, --verbose`         | Show detailed information on space usage 



-----
### docker system events
Get real time events from the server

```bash
docker system events [OPTIONS]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --filter filter`   | Filter output based on conditions provided 
`--format string`       | Format the output using the given Go template 
`--since string`        | Show all events created since timestamp 
`--until string`        | Stream events until this timestamp 



-----
### docker system info
Display system-wide information

```bash
docker system info [OPTIONS]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --format string`   | Format the output using the given Go template 



-----
### docker system prune
Remove unused data

```bash
docker system prune [OPTIONS]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-a, --all`             | Remove all unused images not just dangling ones 
`--filter filter`       | Provide filter values (e.g. 'label=&#60;key&#62;=&#60;value&#62;') 
`-f, --force`           | Do not prompt for confirmation 
`--volumes`             | Prune volumes 



-----
## docker trust
Manage trust on Docker images

```bash
docker trust COMMAND
```

### Management Commands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 `docker trust key`        | Manage keys for signing Docker images 
 `docker trust signer`     | Manage entities who can sign Docker images 


### Commands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 `docker trust inspect`    | Return low-level information about keys and signatures 
 `docker trust revoke`     | Remove trust for an image 
 `docker trust sign`       | Sign an image 


### docker trust key
Manage keys for signing Docker images

```bash
docker trust key COMMAND
```

### Commands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 `docker trust key generate` | Generate and load a signing key-pair 
 `docker trust key load`   | Load a private key file for signing 


#### docker trust key generate
Generate and load a signing key-pair

```bash
docker trust key generate NAME
```

#### Options: 

Options | Description 
-------------------- | -------------------------------------------------- 
`--dir string`       | Directory to generate key in, defaults to current directory 



-----
#### docker trust key load
Load a private key file for signing

```bash
docker trust key load [OPTIONS] KEYFILE
```

#### Options: 

Options | Description 
--------------------- | ------------------------------------------------- 
`--name string`       | Name for the loaded key (default "signer") 



-----
### docker trust signer
Manage entities who can sign Docker images

```bash
docker trust signer COMMAND
```

### Commands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 `docker trust signer add` | Add a signer 
 `docker trust signer remove` | Remove a signer 


#### docker trust signer add
Add a signer

```bash
docker trust signer add OPTIONS NAME REPOSITORY [REPOSITORY...]
```

#### Options: 

Options | Description 
------------------ | ---------------------------------------------------- 
`--key list`       | Path to the signer's public key file 



-----
#### docker trust signer remove
Remove a signer

```bash
docker trust signer remove [OPTIONS] NAME REPOSITORY [REPOSITORY...]
```

#### Options: 

Options | Description 
--------------- | ------------------------------------------------------- 
`-f, --force`   | Do not prompt for confirmation before removing the most recent signer 



-----
### docker trust inspect
Return low-level information about keys and signatures

```bash
docker trust inspect IMAGE[:TAG] [IMAGE[:TAG]...]
```

#### Options: 

Options | Description 
---------------- | ------------------------------------------------------ 
`--pretty`       | Print the information in a human friendly format 



-----
### docker trust revoke
Remove trust for an image

```bash
docker trust revoke [OPTIONS] IMAGE[:TAG]
```

#### Options: 

Options | Description 
------------- | --------------------------------------------------------- 
`-y, --yes`   | Do not prompt for confirmation 



-----
### docker trust sign
Sign an image

```bash
docker trust sign IMAGE:TAG
```

#### Options: 

Options | Description 
--------------- | ------------------------------------------------------- 
`--local`       | Sign a locally tagged image 



-----
## docker volume
Manage volumes

```bash
docker volume COMMAND
```

### Commands: 

 Command                   | Description 
 ------------------------- | --------------------------------------------- 
 `docker volume create`    | Create a volume 
 `docker volume inspect`   | Display detailed information on one or more volumes 
 `docker volume ls`        | List volumes 
 `docker volume prune`     | Remove all unused local volumes 
 `docker volume rm`        | Remove one or more volumes 


### docker volume create
Create a volume

```bash
docker volume create [OPTIONS] [VOLUME]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-d, --driver string`   | Specify volume driver name (default "local") 
`--label list`          | Set metadata for a volume 
`-o, --opt map`         | Set driver specific options (default map[]) 



-----
### docker volume inspect
Display detailed information on one or more volumes

```bash
docker volume inspect [OPTIONS] VOLUME [VOLUME...]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --format string`   | Format the output using the given Go template 



-----
### docker volume ls
List volumes

```bash
docker volume ls [OPTIONS]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --filter filter`   | Provide filter values (e.g. 'dangling=true') 
`--format string`       | Pretty-print volumes using a Go template 
`-q, --quiet`           | Only display volume names 



-----
### docker volume prune
Remove all unused local volumes

```bash
docker volume prune [OPTIONS]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`--filter filter`       | Provide filter values (e.g. 'label=&#60;label&#62;') 
`-f, --force`           | Do not prompt for confirmation 



-----
### docker volume rm
Remove one or more volumes

```bash
docker volume rm [OPTIONS] VOLUME [VOLUME...]
```

#### Options: 

Options | Description 
--------------- | ------------------------------------------------------- 
`-f, --force`   | Force the removal of one or more volumes 



-----
## docker attach
Attach local standard input, output, and error streams to a running container

```bash
docker attach [OPTIONS] CONTAINER
```

#### Options: 

Options | Description 
---------------------------- | ------------------------------------------ 
`--detach-keys string`       | Override the key sequence for detaching a container 
`--no-stdin`                 | Do not attach STDIN 
`--sig-proxy`                | Proxy all received signals to the process (default true) 



-----
## docker build
Build an image from a Dockerfile

```bash
docker build [OPTIONS] PATH | URL | -
```

#### Options: 

Options | Description 
------------------------------- | --------------------------------------- 
`--add-host list`               | Add a custom host-to-IP mapping (host:ip) 
`--build-arg list`              | Set build-time variables 
`--cache-from strings`          | Images to consider as cache sources 
`--cgroup-parent string`        | Optional parent cgroup for the container 
`--compress`                    | Compress the build context using gzip 
`--cpu-period int`              | Limit the CPU CFS (Completely Fair Scheduler) period 
`--cpu-quota int`               | Limit the CPU CFS (Completely Fair Scheduler) quota 
`-c, --cpu-shares int`          | CPU shares (relative weight) 
`--cpuset-cpus string`          | CPUs in which to allow execution (0-3, 0,1) 
`--cpuset-mems string`          | MEMs in which to allow execution (0-3, 0,1) 
`--disable-content-trust`       | Skip image verification (default true) 
`-f, --file string`             | Name of the Dockerfile (Default is 'PATH/Dockerfile') 
`--force-rm`                    | Always remove intermediate containers 
`--iidfile string`              | Write the image ID to the file 
`--isolation string`            | Container isolation technology 
`--label list`                  | Set metadata for an image 
`-m, --memory bytes`            | Memory limit 
`--memory-swap bytes`           | Swap limit equal to memory plus swap: '-1' to enable unlimited swap 
`--network string`              | Set the networking mode for the RUN instructions during build (default "default") 
`--no-cache`                    | Do not use cache when building the image 
`--platform string`             | Set platform if server is multi-platform capable 
`--pull`                        | Always attempt to pull a newer version of the image 
`-q, --quiet`                   | Suppress the build output and print image ID on success 
`--rm`                          | Remove intermediate containers after a successful build (default true) 
`--security-opt strings`        | Security options 
`--shm-size bytes`              | Size of /dev/shm 
`--squash`                      | Squash newly built layers into a single new layer 
`--stream`                      | Stream attaches to server to negotiate build context 
`-t, --tag list`                | Name and optionally a tag in the 'name:tag' format 
`--target string`               | Set the target build stage to build. 
`--ulimit ulimit`               | Ulimit options (default []) 



-----
## docker commit
Create a new image from a container's changes

```bash
docker commit [OPTIONS] CONTAINER [REPOSITORY[:TAG]]
```

#### Options: 

Options | Description 
------------------------ | ---------------------------------------------- 
`-a, --author string`    | Author (e.g., "John Hannibal Smith &#60;hannibal&#64;a-team.com&#62;") 
`-c, --change list`      | Apply Dockerfile instruction to the created image 
`-m, --message string`   | Commit message 
`-p, --pause`            | Pause container during commit (default true) 



-----
## docker cp
Copy files/folders between a container and the local filesystem

```bash
docker cp [OPTIONS] CONTAINER:SRC_PATH DEST_PATH|-
```

#### Options: 

Options | Description 
--------------------- | ------------------------------------------------- 
`-a, --archive`       | Archive mode (copy all uid/gid information) 
`-L, --follow-link`   | Always follow symbol link in SRC_PATH 



-----
## docker create
Create a new container

```bash
docker create [OPTIONS] IMAGE [COMMAND] [ARG...]
```

#### Options: 

Options | Description 
-------------------------------------- | -------------------------------- 
`--add-host list`                      | Add a custom host-to-IP mapping (host:ip) 
`-a, --attach list`                    | Attach to STDIN, STDOUT or STDERR 
`--blkio-weight uint16`                | Block IO (relative weight), between 10 and 1000, or 0 to disable (default 0) 
`--blkio-weight-device list`           | Block IO weight (relative device weight) (default []) 
`--cap-add list`                       | Add Linux capabilities 
`--cap-drop list`                      | Drop Linux capabilities 
`--cgroup-parent string`               | Optional parent cgroup for the container 
`--cidfile string`                     | Write the container ID to the file 
`--cpu-period int`                     | Limit CPU CFS (Completely Fair Scheduler) period 
`--cpu-quota int`                      | Limit CPU CFS (Completely Fair Scheduler) quota 
`--cpu-rt-period int`                  | Limit CPU real-time period in microseconds 
`--cpu-rt-runtime int`                 | Limit CPU real-time runtime in microseconds 
`-c, --cpu-shares int`                 | CPU shares (relative weight) 
`--cpus decimal`                       | Number of CPUs 
`--cpuset-cpus string`                 | CPUs in which to allow execution (0-3, 0,1) 
`--cpuset-mems string`                 | MEMs in which to allow execution (0-3, 0,1) 
`--device list`                        | Add a host device to the container 
`--device-cgroup-rule list`            | Add a rule to the cgroup allowed devices list 
`--device-read-bps list`               | Limit read rate (bytes per second) from a device (default []) 
`--device-read-iops list`              | Limit read rate (IO per second) from a device (default []) 
`--device-write-bps list`              | Limit write rate (bytes per second) to a device (default []) 
`--device-write-iops list`             | Limit write rate (IO per second) to a device (default []) 
`--disable-content-trust`              | Skip image verification (default true) 
`--dns list`                           | Set custom DNS servers 
`--dns-option list`                    | Set DNS options 
`--dns-search list`                    | Set custom DNS search domains 
`--entrypoint string`                  | Overwrite the default ENTRYPOINT of the image 
`-e, --env list`                       | Set environment variables 
`--env-file list`                      | Read in a file of environment variables 
`--expose list`                        | Expose a port or a range of ports 
`--group-add list`                     | Add additional groups to join 
`--health-cmd string`                  | Command to run to check health 
`--health-interval duration`           | Time between running the check (ms&#124;s&#124;m&#124;h) (default 0s) 
`--health-retries int`                 | Consecutive failures needed to report unhealthy 
`--health-start-period duration`       | Start period for the container to initialize before starting health-retries countdown (ms&#124;s&#124;m&#124;h) (default 0s) 
`--health-timeout duration`            | Maximum time to allow one check to run (ms&#124;s&#124;m&#124;h) (default 0s) 
`--help`                               | Print usage 
`-h, --hostname string`                | Container host name 
`--init`                               | Run an init inside the container that forwards signals and reaps processes 
`-i, --interactive`                    | Keep STDIN open even if not attached 
`--ip string`                          | IPv4 address (e.g., 172.30.100.104) 
`--ip6 string`                         | IPv6 address (e.g., 2001:db8::33) 
`--ipc string`                         | IPC mode to use 
`--isolation string`                   | Container isolation technology 
`--kernel-memory bytes`                | Kernel memory limit 
`-l, --label list`                     | Set meta data on a container 
`--label-file list`                    | Read in a line delimited file of labels 
`--link list`                          | Add link to another container 
`--link-local-ip list`                 | Container IPv4/IPv6 link-local addresses 
`--log-driver string`                  | Logging driver for the container 
`--log-opt list`                       | Log driver options 
`--mac-address string`                 | Container MAC address (e.g., 92:d0:c6:0a:29:33) 
`-m, --memory bytes`                   | Memory limit 
`--memory-reservation bytes`           | Memory soft limit 
`--memory-swap bytes`                  | Swap limit equal to memory plus swap: '-1' to enable unlimited swap 
`--memory-swappiness int`              | Tune container memory swappiness (0 to 100) (default -1) 
`--mount mount`                        | Attach a filesystem mount to the container 
`--name string`                        | Assign a name to the container 
`--network string`                     | Connect a container to a network (default "default") 
`--network-alias list`                 | Add network-scoped alias for the container 
`--no-healthcheck`                     | Disable any container-specified HEALTHCHECK 
`--oom-kill-disable`                   | Disable OOM Killer 
`--oom-score-adj int`                  | Tune host's OOM preferences (-1000 to 1000) 
`--pid string`                         | PID namespace to use 
`--pids-limit int`                     | Tune container pids limit (set -1 for unlimited) 
`--platform string`                    | Set platform if server is multi-platform capable 
`--privileged`                         | Give extended privileges to this container 
`-p, --publish list`                   | Publish a container's port(s) to the host 
`-P, --publish-all`                    | Publish all exposed ports to random ports 
`--read-only`                          | Mount the container's root filesystem as read only 
`--restart string`                     | Restart policy to apply when a container exits (default "no") 
`--rm`                                 | Automatically remove the container when it exits 
`--runtime string`                     | Runtime to use for this container 
`--security-opt list`                  | Security Options 
`--shm-size bytes`                     | Size of /dev/shm 
`--stop-signal string`                 | Signal to stop a container (default "SIGTERM") 
`--stop-timeout int`                   | Timeout (in seconds) to stop a container 
`--storage-opt list`                   | Storage driver options for the container 
`--sysctl map`                         | Sysctl options (default map[]) 
`--tmpfs list`                         | Mount a tmpfs directory 
`-t, --tty`                            | Allocate a pseudo-TTY 
`--ulimit ulimit`                      | Ulimit options (default []) 
`-u, --user string`                    | Username or UID (format: &#60;name&#124;uid&#62;[:&#60;group&#124;gid&#62;]) 
`--userns string`                      | User namespace to use 
`--uts string`                         | UTS namespace to use 
`-v, --volume list`                    | Bind mount a volume 
`--volume-driver string`               | Optional volume driver for the container 
`--volumes-from list`                  | Mount volumes from the specified container(s) 
`-w, --workdir string`                 | Working directory inside the container 



-----
## docker deploy
Deploy a new stack or update an existing stack

```bash
docker deploy [OPTIONS] STACK
```

#### Options: 

Options | Description 
------------------------------ | ---------------------------------------- 
`--bundle-file string`         | Path to a Distributed Application Bundle file 
`-c, --compose-file strings`   | Path to a Compose file 
`--prune`                      | Prune services that are no longer referenced 
`--resolve-image string`       | Query the registry to resolve image digest and supported platforms ("always"&#124;"changed"&#124;"never") (default "always") 
`--with-registry-auth`         | Send registry authentication details to Swarm agents 



-----
## docker diff
Inspect changes to files or directories on a container's filesystem

```bash
docker diff CONTAINER
```


-----
## docker events
Get real time events from the server

```bash
docker events [OPTIONS]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --filter filter`   | Filter output based on conditions provided 
`--format string`       | Format the output using the given Go template 
`--since string`        | Show all events created since timestamp 
`--until string`        | Stream events until this timestamp 



-----
## docker exec
Run a command in a running container

```bash
docker exec [OPTIONS] CONTAINER COMMAND [ARG...]
```

#### Options: 

Options | Description 
---------------------------- | ------------------------------------------ 
`-d, --detach`               | Detached mode: run command in the background 
`--detach-keys string`       | Override the key sequence for detaching a container 
`-e, --env list`             | Set environment variables 
`-i, --interactive`          | Keep STDIN open even if not attached 
`--privileged`               | Give extended privileges to the command 
`-t, --tty`                  | Allocate a pseudo-TTY 
`-u, --user string`          | Username or UID (format: &#60;name&#124;uid&#62;[:&#60;group&#124;gid&#62;]) 
`-w, --workdir string`       | Working directory inside the container 



-----
## docker export
Export a container's filesystem as a tar archive

```bash
docker export [OPTIONS] CONTAINER
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-o, --output string`   | Write to a file, instead of STDOUT 



-----
## docker history
Show the history of an image

```bash
docker history [OPTIONS] IMAGE
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`--format string`       | Pretty-print images using a Go template 
`-H, --human`           | Print sizes and dates in human readable format (default true) 
`--no-trunc`            | Don't truncate output 
`-q, --quiet`           | Only show numeric IDs 



-----
## docker images
List images

```bash
docker images [OPTIONS] [REPOSITORY[:TAG]]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-a, --all`             | Show all images (default hides intermediate images) 
`--digests`             | Show digests 
`-f, --filter filter`   | Filter output based on conditions provided 
`--format string`       | Pretty-print images using a Go template 
`--no-trunc`            | Don't truncate output 
`-q, --quiet`           | Only show numeric IDs 



-----
## docker import
Import the contents from a tarball to create a filesystem image

```bash
docker import [OPTIONS] file|URL|- [REPOSITORY[:TAG]]
```

#### Options: 

Options | Description 
------------------------ | ---------------------------------------------- 
`-c, --change list`      | Apply Dockerfile instruction to the created image 
`-m, --message string`   | Set commit message for imported image 



-----
## docker info
Display system-wide information

```bash
docker info [OPTIONS]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --format string`   | Format the output using the given Go template 



-----
## docker inspect
Return low-level information on Docker objects

```bash
docker inspect [OPTIONS] NAME|ID [NAME|ID...]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --format string`   | Format the output using the given Go template 
`-s, --size`            | Display total file sizes if the type is container 
`--type string`         | Return JSON for specified type 



-----
## docker kill
Kill one or more running containers

```bash
docker kill [OPTIONS] CONTAINER [CONTAINER...]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-s, --signal string`   | Signal to send to the container (default "KILL") 



-----
## docker load
Load an image from a tar archive or STDIN

```bash
docker load [OPTIONS]
```

#### Options: 

Options | Description 
---------------------- | ------------------------------------------------ 
`-i, --input string`   | Read from tar archive file, instead of STDIN 
`-q, --quiet`          | Suppress the load output 



-----
## docker login
Log in to a Docker registry

```bash
docker login [OPTIONS] [SERVER]
```

#### Options: 

Options | Description 
------------------------- | --------------------------------------------- 
`-p, --password string`   | Password 
`--password-stdin`        | Take the password from stdin 
`-u, --username string`   | Username 



-----
## docker logout
Log out from a Docker registry

```bash
docker logout [SERVER]
```


-----
## docker logs
Fetch the logs of a container

```bash
docker logs [OPTIONS] CONTAINER
```

#### Options: 

Options | Description 
---------------------- | ------------------------------------------------ 
`--details`            | Show extra details provided to logs 
`-f, --follow`         | Follow log output 
`--since string`       | Show logs since timestamp (e.g. 2013-01-02T13:23:37) or relative (e.g. 42m for 42 minutes) 
`--tail string`        | Number of lines to show from the end of the logs (default "all") 
`-t, --timestamps`     | Show timestamps 
`--until string`       | Show logs before a timestamp (e.g. 2013-01-02T13:23:37) or relative (e.g. 42m for 42 minutes) 



-----
## docker pause
Pause all processes within one or more containers

```bash
docker pause CONTAINER [CONTAINER...]
```


-----
## docker port
List port mappings or a specific mapping for the container

```bash
docker port CONTAINER [PRIVATE_PORT[/PROTO]]
```


-----
## docker ps
List containers

```bash
docker ps [OPTIONS]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-a, --all`             | Show all containers (default shows just running) 
`-f, --filter filter`   | Filter output based on conditions provided 
`--format string`       | Pretty-print containers using a Go template 
`-n, --last int`        | Show n last created containers (includes all states) (default -1) 
`-l, --latest`          | Show the latest created container (includes all states) 
`--no-trunc`            | Don't truncate output 
`-q, --quiet`           | Only display numeric IDs 
`-s, --size`            | Display total file sizes 



-----
## docker pull
Pull an image or a repository from a registry

```bash
docker pull [OPTIONS] NAME[:TAG|@DIGEST]
```

#### Options: 

Options | Description 
------------------------------- | --------------------------------------- 
`-a, --all-tags`                | Download all tagged images in the repository 
`--disable-content-trust`       | Skip image verification (default true) 
`--platform string`             | Set platform if server is multi-platform capable 



-----
## docker push
Push an image or a repository to a registry

```bash
docker push [OPTIONS] NAME[:TAG]
```

#### Options: 

Options | Description 
------------------------------- | --------------------------------------- 
`--disable-content-trust`       | Skip image signing (default true) 



-----
## docker rename
Rename a container

```bash
docker rename CONTAINER NEW_NAME
```


-----
## docker restart
Restart one or more containers

```bash
docker restart [OPTIONS] CONTAINER [CONTAINER...]
```

#### Options: 

Options | Description 
------------------ | ---------------------------------------------------- 
`-t, --time int`   | Seconds to wait for stop before killing the container (default 10) 



-----
## docker rm
Remove one or more containers

```bash
docker rm [OPTIONS] CONTAINER [CONTAINER...]
```

#### Options: 

Options | Description 
----------------- | ----------------------------------------------------- 
`-f, --force`     | Force the removal of a running container (uses SIGKILL) 
`-l, --link`      | Remove the specified link 
`-v, --volumes`   | Remove the volumes associated with the container 



-----
## docker rmi
Remove one or more images

```bash
docker rmi [OPTIONS] IMAGE [IMAGE...]
```

#### Options: 

Options | Description 
------------------ | ---------------------------------------------------- 
`-f, --force`      | Force removal of the image 
`--no-prune`       | Do not delete untagged parents 



-----
## docker run
Run a command in a new container

```bash
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```

#### Options: 

Options | Description 
-------------------------------------- | -------------------------------- 
`--add-host list`                      | Add a custom host-to-IP mapping (host:ip) 
`-a, --attach list`                    | Attach to STDIN, STDOUT or STDERR 
`--blkio-weight uint16`                | Block IO (relative weight), between 10 and 1000, or 0 to disable (default 0) 
`--blkio-weight-device list`           | Block IO weight (relative device weight) (default []) 
`--cap-add list`                       | Add Linux capabilities 
`--cap-drop list`                      | Drop Linux capabilities 
`--cgroup-parent string`               | Optional parent cgroup for the container 
`--cidfile string`                     | Write the container ID to the file 
`--cpu-period int`                     | Limit CPU CFS (Completely Fair Scheduler) period 
`--cpu-quota int`                      | Limit CPU CFS (Completely Fair Scheduler) quota 
`--cpu-rt-period int`                  | Limit CPU real-time period in microseconds 
`--cpu-rt-runtime int`                 | Limit CPU real-time runtime in microseconds 
`-c, --cpu-shares int`                 | CPU shares (relative weight) 
`--cpus decimal`                       | Number of CPUs 
`--cpuset-cpus string`                 | CPUs in which to allow execution (0-3, 0,1) 
`--cpuset-mems string`                 | MEMs in which to allow execution (0-3, 0,1) 
`-d, --detach`                         | Run container in background and print container ID 
`--detach-keys string`                 | Override the key sequence for detaching a container 
`--device list`                        | Add a host device to the container 
`--device-cgroup-rule list`            | Add a rule to the cgroup allowed devices list 
`--device-read-bps list`               | Limit read rate (bytes per second) from a device (default []) 
`--device-read-iops list`              | Limit read rate (IO per second) from a device (default []) 
`--device-write-bps list`              | Limit write rate (bytes per second) to a device (default []) 
`--device-write-iops list`             | Limit write rate (IO per second) to a device (default []) 
`--disable-content-trust`              | Skip image verification (default true) 
`--dns list`                           | Set custom DNS servers 
`--dns-option list`                    | Set DNS options 
`--dns-search list`                    | Set custom DNS search domains 
`--entrypoint string`                  | Overwrite the default ENTRYPOINT of the image 
`-e, --env list`                       | Set environment variables 
`--env-file list`                      | Read in a file of environment variables 
`--expose list`                        | Expose a port or a range of ports 
`--group-add list`                     | Add additional groups to join 
`--health-cmd string`                  | Command to run to check health 
`--health-interval duration`           | Time between running the check (ms&#124;s&#124;m&#124;h) (default 0s) 
`--health-retries int`                 | Consecutive failures needed to report unhealthy 
`--health-start-period duration`       | Start period for the container to initialize before starting health-retries countdown (ms&#124;s&#124;m&#124;h) (default 0s) 
`--health-timeout duration`            | Maximum time to allow one check to run (ms&#124;s&#124;m&#124;h) (default 0s) 
`--help`                               | Print usage 
`-h, --hostname string`                | Container host name 
`--init`                               | Run an init inside the container that forwards signals and reaps processes 
`-i, --interactive`                    | Keep STDIN open even if not attached 
`--ip string`                          | IPv4 address (e.g., 172.30.100.104) 
`--ip6 string`                         | IPv6 address (e.g., 2001:db8::33) 
`--ipc string`                         | IPC mode to use 
`--isolation string`                   | Container isolation technology 
`--kernel-memory bytes`                | Kernel memory limit 
`-l, --label list`                     | Set meta data on a container 
`--label-file list`                    | Read in a line delimited file of labels 
`--link list`                          | Add link to another container 
`--link-local-ip list`                 | Container IPv4/IPv6 link-local addresses 
`--log-driver string`                  | Logging driver for the container 
`--log-opt list`                       | Log driver options 
`--mac-address string`                 | Container MAC address (e.g., 92:d0:c6:0a:29:33) 
`-m, --memory bytes`                   | Memory limit 
`--memory-reservation bytes`           | Memory soft limit 
`--memory-swap bytes`                  | Swap limit equal to memory plus swap: '-1' to enable unlimited swap 
`--memory-swappiness int`              | Tune container memory swappiness (0 to 100) (default -1) 
`--mount mount`                        | Attach a filesystem mount to the container 
`--name string`                        | Assign a name to the container 
`--network string`                     | Connect a container to a network (default "default") 
`--network-alias list`                 | Add network-scoped alias for the container 
`--no-healthcheck`                     | Disable any container-specified HEALTHCHECK 
`--oom-kill-disable`                   | Disable OOM Killer 
`--oom-score-adj int`                  | Tune host's OOM preferences (-1000 to 1000) 
`--pid string`                         | PID namespace to use 
`--pids-limit int`                     | Tune container pids limit (set -1 for unlimited) 
`--platform string`                    | Set platform if server is multi-platform capable 
`--privileged`                         | Give extended privileges to this container 
`-p, --publish list`                   | Publish a container's port(s) to the host 
`-P, --publish-all`                    | Publish all exposed ports to random ports 
`--read-only`                          | Mount the container's root filesystem as read only 
`--restart string`                     | Restart policy to apply when a container exits (default "no") 
`--rm`                                 | Automatically remove the container when it exits 
`--runtime string`                     | Runtime to use for this container 
`--security-opt list`                  | Security Options 
`--shm-size bytes`                     | Size of /dev/shm 
`--sig-proxy`                          | Proxy received signals to the process (default true) 
`--stop-signal string`                 | Signal to stop a container (default "SIGTERM") 
`--stop-timeout int`                   | Timeout (in seconds) to stop a container 
`--storage-opt list`                   | Storage driver options for the container 
`--sysctl map`                         | Sysctl options (default map[]) 
`--tmpfs list`                         | Mount a tmpfs directory 
`-t, --tty`                            | Allocate a pseudo-TTY 
`--ulimit ulimit`                      | Ulimit options (default []) 
`-u, --user string`                    | Username or UID (format: &#60;name&#124;uid&#62;[:&#60;group&#124;gid&#62;]) 
`--userns string`                      | User namespace to use 
`--uts string`                         | UTS namespace to use 
`-v, --volume list`                    | Bind mount a volume 
`--volume-driver string`               | Optional volume driver for the container 
`--volumes-from list`                  | Mount volumes from the specified container(s) 
`-w, --workdir string`                 | Working directory inside the container 



-----
## docker save
Save one or more images to a tar archive (streamed to STDOUT by default)

```bash
docker save [OPTIONS] IMAGE [IMAGE...]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-o, --output string`   | Write to a file, instead of STDOUT 



-----
## docker search
Search the Docker Hub for images

```bash
docker search [OPTIONS] TERM
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --filter filter`   | Filter output based on conditions provided 
`--format string`       | Pretty-print search using a Go template 
`--limit int`           | Max number of search results (default 25) 
`--no-trunc`            | Don't truncate output 



-----
## docker start
Start one or more stopped containers

```bash
docker start [OPTIONS] CONTAINER [CONTAINER...]
```

#### Options: 

Options | Description 
------------------------------- | --------------------------------------- 
`-a, --attach`                  | Attach STDOUT/STDERR and forward signals 
`--checkpoint string`           | Restore from this checkpoint 
`--checkpoint-dir string`       | Use a custom checkpoint storage directory 
`--detach-keys string`          | Override the key sequence for detaching a container 
`-i, --interactive`             | Attach container's STDIN 



-----
## docker stats
Display a live stream of container(s) resource usage statistics

```bash
docker stats [OPTIONS] [CONTAINER...]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-a, --all`             | Show all containers (default shows just running) 
`--format string`       | Pretty-print images using a Go template 
`--no-stream`           | Disable streaming stats and only pull the first result 
`--no-trunc`            | Do not truncate output 



-----
## docker stop
Stop one or more running containers

```bash
docker stop [OPTIONS] CONTAINER [CONTAINER...]
```

#### Options: 

Options | Description 
------------------ | ---------------------------------------------------- 
`-t, --time int`   | Seconds to wait for stop before killing it (default 10) 



-----
## docker tag
Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE

```bash
docker tag SOURCE_IMAGE[:TAG] TARGET_IMAGE[:TAG]
```


-----
## docker top
Display the running processes of a container

```bash
docker top CONTAINER [ps OPTIONS]
```


-----
## docker unpause
Unpause all processes within one or more containers

```bash
docker unpause CONTAINER [CONTAINER...]
```


-----
## docker update
Update configuration of one or more containers

```bash
docker update [OPTIONS] CONTAINER [CONTAINER...]
```

#### Options: 

Options | Description 
---------------------------------- | ------------------------------------ 
`--blkio-weight uint16`            | Block IO (relative weight), between 10 and 1000, or 0 to disable (default 0) 
`--cpu-period int`                 | Limit CPU CFS (Completely Fair Scheduler) period 
`--cpu-quota int`                  | Limit CPU CFS (Completely Fair Scheduler) quota 
`--cpu-rt-period int`              | Limit the CPU real-time period in microseconds 
`--cpu-rt-runtime int`             | Limit the CPU real-time runtime in microseconds 
`-c, --cpu-shares int`             | CPU shares (relative weight) 
`--cpus decimal`                   | Number of CPUs 
`--cpuset-cpus string`             | CPUs in which to allow execution (0-3, 0,1) 
`--cpuset-mems string`             | MEMs in which to allow execution (0-3, 0,1) 
`--kernel-memory bytes`            | Kernel memory limit 
`-m, --memory bytes`               | Memory limit 
`--memory-reservation bytes`       | Memory soft limit 
`--memory-swap bytes`              | Swap limit equal to memory plus swap: '-1' to enable unlimited swap 
`--restart string`                 | Restart policy to apply when a container exits 



-----
## docker version
Show the Docker version information

```bash
docker version [OPTIONS]
```

#### Options: 

Options | Description 
----------------------- | ----------------------------------------------- 
`-f, --format string`   | Format the output using the given Go template 



-----
## docker wait
Block until one or more containers stop, then print their exit codes

```bash
docker wait CONTAINER [CONTAINER...]
```