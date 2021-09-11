---
title: Docker permission denied in LXD container
tags:
- docker
- LXD

---



#### Docker run errors in LXD container

```bash
docker: Error response from daemon: failed to create shim: OCI runtime create failed: container_linux.go:380: starting container process caused: process_linux.go:545: container init caused: rootfs_linux.go:76: mounting "proc" to rootfs at "/proc" caused: mount through procfd: permission denied: unknown.
```

##### *This is resulting from the security setting of LXD container.*



#### Solution:

###### For new container:

```bash
lxc launch ubuntu  -c security.nesting=true
```

###### For a currently running container:

```bash
lxc stop container

lxc config set container security.nesting true

lxc start container
```

