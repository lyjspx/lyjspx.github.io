---
title: One rJava problem in R
tags:
- R
---

New version of R has wrong path of libjvm.so

Error pops up: 

```
libjvm.so: cannot open shared object file: No such file or directory
```

Solution (From https://stackoverflow.com/questions/28462302):

1. Find your R location. It will be stored in `rsession-ld-library-path` in `rserver.conf` file. Or just by doing `which R`. The location usually is `/usr/lib64/R/lib` or `/usr/lib64/microsoft-r/3.3/lib64/R/lib`
2. Find the `libjvm.so` file which is usually in the `usr/lib/jvm/java-8-openjdk-amd64/jre/lib/amd64/server` path depending on which jre you're using. Check in $JAVA_HOME environment.
3. Create a symlink using `ln -s` `sudo ln -s /usr/lib/jvm/java-8-openjdk-amd64/jre/lib/amd64/server/libjvm.so /usr/lib64/microsoft-r/3.3/lib64/R/lib/libjvm.so`
4. Restart R server

