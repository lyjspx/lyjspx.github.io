---
title: Rstudio server stuck in loading page
tags:
- Rstudio_server
---

Sometimes, RStudio server always stuck in the loading page, especially exiting abnormally in last run. Use systemctl restart rstudioserver or restart docker do not solve the problem. The reason is that Rstudio automatically resume the last running environment. However, when something wrong, Rstudio always try to resume a bad environment in a dead loop. 

Solution:

Delete cached session files.

~/.local/share/rstudio/session (update version)

~/.rstudio/session (old version)
