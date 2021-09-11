---
title: Rstudio server docker commands
tags:
- Rstudio_server
- docker

---

#### Launch docker container

```bash
 docker run -d -ti  --rm -p 8787:8787 -e ROOT=TRUE  -e PASSWORD=yourpasswordhere --name RStudioServer --mount source=R_data,target=/home/rstudio/rdata  rstudio
```

-d: detach

-t: psudo-terminal

-i: interactive

--rm: clean up 

#### Port forwarding of the host

```bash
lxc config device add mycontainer myport80 proxy listen=tcp:0.0.0.0:80 connect=tcp:127.0.0.1:80 
```

