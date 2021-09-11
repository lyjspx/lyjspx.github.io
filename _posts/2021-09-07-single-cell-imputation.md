---
title: Single Cell Imputation
tags:
- Bioinformatics
---

### scImpute

> ```R
> scimpute(# full path to raw count matrix                                                                     
>     count_path = '/home/ubuntu/download/cart/AHCA.nonimmu.trachea.csv',                                   
>     infile = "csv",           # format of input file                                                      
>     outfile = "csv",          # format of output file                                                     
>     out_dir = "/home/ubuntu/download/cart/AHCA.nonimmu.trachea.scimpute_dropprob0.3", # full path to output directory                                                                                           
>     labeled = FALSE,          # cell type labels not available                                            
>     drop_thre = 0.3,          # threshold set on dropout probability                                      
>     Kcluster = 2,             # 2 cell subpopulations                                                     
>     ncores = 24)              # number of cores used in parallel computation
> ```



### DrImpute

```R
X = read.csv('/home/ubuntu/download/cart/AHCA.nonimmu.trachea.csv')
dim(X)
X.log <- log(X + 1)
X.log <- as.matrix(X.log)  
set.seed(1)
X.imp <- DrImpute(X.log, mc.cores=20) 
X.imp.count = exp(X.imp) - 1 
write.csv(X.imp.count,'/home/ubuntu/download/cart/AHCA.trachea.drimpute.csv')   

```

