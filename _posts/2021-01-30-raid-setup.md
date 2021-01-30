---
tags:
- 'Linux'
- disk
title: RAID setup
---

## Two RAID solutions
Hardware: PCIE RAID card
Software: Linux softwares


---
A workstation in our lab uses hardware PCIE RAID card to maintain disks.
All disks connect to PCIE RAID card.
RAID card is setup in BIOS. 

**Before entering system, virtual drive must be created. **
Systems can not identify any physical disks. Only when virtual drive is setup, can system identify drives.

Foreign in RAID means the disk contains RAID configuration that does not belong to the current RAID card.
Foreign configuration can be imported or wiped.

---
Software-based RAID is managed by programs (e.g., mdadm).
The programs merge mounting points into single virtual drive.
