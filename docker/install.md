# Install docker on Debian stable The correct way

 ## Debian Based
 
 ```
 $ sudo apt install docker.io docker-compose
 $ sudo usermod -aG docker ${USER}
```

## Now you can use docker with regular user without sudo
```
$ docker ps
```


## Test Installation
```
$ id -nG
$ groups ${USER}

$ docker run hello-world
```


