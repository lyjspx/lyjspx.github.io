---
title: Linux with cloud drive - Dropbox
tags:
- Linux
---

Among these popular Cloud Drive service providers, Dropbox is the **only** **one** offering official Linux client. However, errors wll pop up when starting the service.  The reason is some dependencies missing in Ubuntu 20.04.

Solution:

```bash
sudo apt install libc6 libglapi-mesa libxdamage1 libxfixes3 libxcb-glx0 libxcb-dri2-0 libxcb-dri3-0 libxcb-present0 libxcb-sync1 libxshmfence1 libxxf86vm1
```

The Dropbox will generate a unique one-time link, and user need to copy this link into a browser to authorize the action.

Once the service running, the Dropbox will sync your library under the home folder.

