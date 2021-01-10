---
title: Rstudio server in LXD container combined with conda environment
tags:
- Rstudio
- Rstudio_server
- LXD
---

Rstudio server in LXD container combined with conda environment

I have a conda environment dedicated to the R studio server. Rstudio server is an application service running in the background. 

The start of Rstudio server service cannot combine with conda environment. That means the service will rely on the base environment. 

I attempted to edit systemd file and wrap the start service into a shell script which activates environment first. However, the environment does not start prior to the running of service.

Some R packages from Bioconductor need system libraries. 


Current solution:

Use Rstudio server docker image.

Note:
I have a LXD container running on a server.
Running docker in a LXD container always pops out OCI errors. A change must be made before running docker.

In LXD documentation page, https://lxd.readthedocs.io/en/latest/

How can I run docker inside a LXD container?
In order to run Docker inside a LXD container the security.nesting property of the container should be set to true. 
```
lxc config set <container> security.nesting true
```

Note that LXD containers cannot load kernel modules, so depending on your Docker configuration you may need to have the needed extra kernel modules loaded by the host.
You can do so by setting a comma separate list of kernel modules that your container needs with:
```
lxc config set <container> linux.kernel_modules <modules>
```
We have also received some reports that creating a /.dockerenv file in your container can help Docker ignore some errors it's getting due to running in a nested environment.
