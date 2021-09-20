## Docker commands 

### Command to check the running and past running docker instances

```
docker ps –a 
```

### Run the docker instance

```
docker run –it –-name <somename> -d Ubuntu
```

### Get container id and attach to the docker instance

```
docker ps –l
```

### Exit a docker container

```
exit
```

### Start the docker container

```
Docker start <container id>
```

### Attach docker container id

```
docker attach <container id> 
```

### Commit the container containing the information

```
docker commit <container id>
```

### Use command docker images to check which images are saved.

```
docker list 
```

### docker tag and image with an image name

```
docker tag <image id – one which gets printed post docker commit command> <image name>
```

### docker list containers which are exited

```
docker ps -aq -f status=exited
```

### Remove Stopped Containers 

```
docker ps -aq --no-trunc | xargs docker rm
```
NOte: - This will not remove running containers 

### Remove dangling/untagged images

```
docker images -q --filter dangling=true | xargs docker rmi
```

### Remove containers created after a specific container

```
docker ps --since a1bz3768ez7g -q | xargs docker rm
```

### Remove containers created before a specific container

```
docker ps --before a1bz3768ez7g -q | xargs docker rm
```

### Connect to same docker container

```
Docker exec -it <container id> bash
```
OR
```
docker exec -ti --env COLUMNS=`tput cols` --env LINES=`tput lines` container id bash
```

### Get the information about the command arguments used to start container

```
docker inspect -f '{{ .Config.Env}} {{ .Config.Entrypoint}} {{ .Config.Cmd}} {{ .VolumesFrom}} {{.Volumes}}  {{ .HostConfig.links}}' container_id
```
