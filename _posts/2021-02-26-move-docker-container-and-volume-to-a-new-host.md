---
title: Move docker container and volume to a new host
tags:
- docker
- Linux
---

# Move docker container and volume to another host

## Image and container
My understanding about image and container:
Container is a running image;
Image is a stopped container.

## move a container
* export current container (files) into a image 
```
docker export <CONTAINER ID> > /home/export.tar
```
*  Transfer to remote host (e.g. sftp)
*  Import image in remote host
```
cat /home/export.tar | docker import - some-name:latest
```


#### Note: 'docker export' exports all files but not command
```
docker run -d -p 8787:8787 -e PASSWORD=yourpasswordhere rocker/rstudio:3.2.0
```
The command of running genunie Rstudio image  does not specifiy a command

When running imported image
```
sudo docker run -d -ti  --rm -p 8787:8787 --name RStudioServer --mount source=R_data,target=/home/rstudio/rdata   rstudio:new
docker: Error response from daemon: No command specified.
```

We need to go back to the original host to find the command:
```
sudo docker ps
d79a11d5b7d0        rocker/rstudio:cancer_prediction   "/init"             15 minutes ago      Up 11 minutes       0.0.0.0:8787->8787/tcp   RStudioServer
```
We can see the command is '/init'

```
sudo docker run -d -ti  --rm -p 8787:8787  --name RStudioServer --mount source=R_data,target=/home/rstudio/rdata   rstudio:fromTesla /init
```

## Move a volume
There is no a magic command to move a volume.
My practise is compressing the whole directory and copying into the new container (mount the same entry point).
