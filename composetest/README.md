
# This is simple docker compose

Docker compose means to run multiple containers as a single service.

For example, an application which required NGNIX and MySQL, we create one file which would start **both the containers as a service** without the need to start each one separately.


### Run

`$ docker-compose up`

change `app.py` will affect program when docker-compose up in running state.

also we can detach docker compose with

`$ docker-compose up -d`

## link

[original source](https://docs.docker.com/compose/gettingstarted/)


WARNING: Image for service web was built because it did not already exist. To rebuild this image you must use `docker-compose build` or `docker-compose up --build`.

---

## Instead of using compose use docker build command

```
$ docker build -t flask_app 
```
