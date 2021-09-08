---
title: Create docker volume device/host path
tags:
- docker
---

Docker recommends creating volumes in the default location. However, designating location will be easy for data transferring. Especially, dockers for internal use will not be exposed to the public, and thus security is not a big issue.

A couple options:

## Copy into container

```bash
docker cp /path/of/the/file <Container_ID>:/path/of/he/container/folder
```

Not a persistent way, because of no volumes involved



## Attach a directory as volume

Create

```bash
docker volume create --name my_test_volume --opt type=none --opt device=/home/../Test_volume --opt o=bind
```

Mount

```bash
docker run -d \
  --name container_name \
  --mount source=my_test_volume,target=/mount_point \
  image_name
```



The two steps are actually modifying the container yaml file and compose it.

```bash
version: '3'
services:
  nginx:
    image: image_name
    ports:
      - "8081:80"
    volumes:
      - my_test_volume:/mount_point
volumes:
  my_test_volume:
    driver: local
    driver_opts:
       o: bind
       type: none
       device: /home/../Test_volume
```

```bash
docker-compose up -d
```

