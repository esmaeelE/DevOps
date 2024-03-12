# docker cheatsheet


## list all commands
Use bash completion write docker then press enter to see docker commands

```
attach     config     create     export     images     kill       logs       pause      pull       rm         search     start      system     unpause    wait
build      container  diff       help       import     load       manifest   plugin     push       rmi        secret     stats      tag        update     
builder    context    events     history    info       login      network    port       rename     run        service    stop       top        version    
commit     cp         exec       image      inspect    logout     node       ps         restart    save       stack      swarm      trust      volume
```

## Get information

### General
```
# General
docker info
docker version

docker system info 
docker system df

docker ps
docker ps -a

# docker htop
docker stats
```

### containers
```
docker container ls
docker container inspect container_name or container_id
```

### images 
```
docker history image_name
docker image ls
```
### network
```
docker network ls
docker network network_name or network_id
# port, get port mapping for containers
docker port container_name or container_ip
```

### volume
```
docker volume ls 
docker volume inspect volume_name
```
