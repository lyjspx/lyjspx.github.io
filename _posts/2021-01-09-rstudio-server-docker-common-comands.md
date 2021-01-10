---
title: Rstudio server Docker common commands
tags:
- docker
- Rstudio
- Rstudio_server
---

```
sudo docker run -d -ti  --rm -p 8787:8787 -e ROOT=TRUE  -e PASSWORD=yourpasswordhere --name RStudioServer --mount source=R_data,target=/home/rstudio/rdata  rocker/rstudio
```

-d: detachable
-e ROOT: give user privileges
-e PASSWORD: define password
--mount: mount a persistent drive
--name: give the container a name

---
Detach and attach for dock containers (copied from a post)
~~~~
It all depends on how the container is launched. It comes down to the following when the container was launched:
was a TTY allocated (-t)
was stdin left open (-i)

^P^Q does work, BUT only when -t and -i is used to launch the container:
```
[berto@g6]$ docker run -ti -d --name test python:3.6 /bin/bash -c 'while [ 1 ]; do sleep 30; done;' b26e39632351192a9a1a00ea0c2f3e10729b6d3e22f8e0676d6519e15c08b518 
[berto@g6]$ docker attach test # here I typed 
```

^P^Q read escape sequence # i'm back to my prompt [berto@g6]$ docker kill test; docker rm -v test test test
ctrl+c does work, BUT only when -t (without -i) is used to launch the container:
```
[berto@g6]$ docker run -t -d --name test python:3.6 /bin/bash -c 'while [ 1 ]; do sleep 30; done;' 018a228c96d6bf2e73cccaefcf656b02753905b9a859f32e60bdf343bcbe834d 
[berto@g6]$ docker attach test ^C 
[berto@g6]$
```
