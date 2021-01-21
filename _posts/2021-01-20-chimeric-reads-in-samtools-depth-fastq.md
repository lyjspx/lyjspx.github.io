---
title: Chimeric reads in Samtools depth & fastq
tags:
- Samtools
---

## Chimeric reads
Reads are splited and aligned to reference genome separately. 
Samtools flag 2048

```
samtools view -F 2048
```
can easliy exclude chimeric reads 

## Different strategies in Samtools fastq & depth

```
samtools fastq
```
does not include any chimeric reads in output file

```
samtools depth
```
However, count all reads including chimeric

**Warning: Output from samtools fastq and samtools depth can be inconsistent **
