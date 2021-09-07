---
title: Sparse Matrix in Single Cell
tags:
- Bioinformatics
- Single_Cell
---

Single Cell technology generates at least billions of data points each time. Explicit reprentation is pretty hard and memory consuming. The most of data points are 0, which can be expression dropout or no expression. Thus, sparse matrix is an appropriate strategy for data storage.  

Sparse matrix in R is not a native data type but a matrix-like object supported by package 'Matrix'.

Be care with using apply, because it will expand this to a matrix first.

Multiprocessing may require load this package

```
foreach( .package = 'Matrix')
```

