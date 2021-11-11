---
title: Unknown n_max parameter in read.table base read function
tags:
- R
---

Last time, I was reading three large tab delimited files into R (4.0.X) using read.table().

1st: 1.2M rows

2nd: 0.8M rows

3rd: 0.3M rows

The function did not fully parse the first file, and only 0.3M rows were susscefully read into memory. No problem was identified in the latter two files. I did not find any support documentation to elucidate the n_max behavior. 

read.delim and read_delim(tidyverse) did fully parse the files.

read.table is **NOT** recommended!

