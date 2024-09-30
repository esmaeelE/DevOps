# Fastest proxy to expose port
```
$ sudo apt install simpleproxy
```


## Run
```
simpleproxy -L 0.0.0.0:8888 -R 127.0.0.1:9090
```

Above command expose our internal server on `127.0.0.1:9090`. 
To access from internet `PublicIP:8888`
