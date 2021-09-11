---
title: Add Host directory to LXD container
tags:
- LXD
- Linux
---

Host directory can be mounted to a container at read-lony or read-write mode.

It looks like LXD officially support one-step configuration from some time. In the previous version, we have to go through serveral steps to mount it in read-write mode. See the conversations.

[Previous version - Example](https://www.cyberciti.biz/faq/how-to-add-or-mount-directory-in-lxd-linux-container/)

Now, we can easily define the mounting mode by tuning readonly flag.

```bash
lxc config device add container name disk source=/data path=/mnt/data readonly=true
```

