---
title: One port - one process, what about multiple tabs and/or browsers
tags:
- network
---

One process listens to one port. 

What about a computer runs multiple tabs/ browsers?

For clients, we don'y listen to port 80. For each tab, the browser will assign an arbitray port (usually > 50000) to the tab. Then, each port independently communicates with each tab. So one process still listens to one port.
