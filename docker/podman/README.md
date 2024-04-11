# Podman containerization

## Install

Just run below commands
```
$ sudo apt install podman podman-compose
```

## Test
```
$ podman version 
Client:       Podman Engine
Version:      4.3.1
API Version:  4.3.1
Go Version:   go1.19.8
Built:        Thu Jan  1 01:00:00 1970
OS/Arch:      linux/amd64


$ podman run hello-world:latest

```
Time is wrong, why?

## Set registry and Iran mirros.
```
```


## change default storage location
podman save containers images and volume in $HOME of running user. we can change it.
for example I placed them in `/var/container/`

```
$ sudo mkdir -p /var/container
$ sudo chowd -R user /var/container/

$ cat ~/.config/containers/storage.conf
[storage]
  driver = "overlay"
  runroot = "/run/user/1000"
  graphroot = "/var/container/storage"
  [storage.options]
    size = ""
    remap-uids = ""
    remap-gids = ""
    ignore_chown_errors = ""
    remap-user = ""
    remap-group = ""
    mount_program = "/usr/bin/fuse-overlayfs"
    mountopt = ""
    [storage.options.thinpool]
      autoextend_percent = ""
      autoextend_threshold = ""
      basesize = ""
      blocksize = ""
      directlvm_device = ""
      directlvm_device_force = ""
      fs = ""
      log_level = ""
      min_free_space = ""
      mkfsarg = ""
      mountopt = ""
      use_deferred_deletion = ""
      use_deferred_removal = ""
      xfs_nospace_max_retries = ""
```
