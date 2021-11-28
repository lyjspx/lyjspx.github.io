---
tags:
- web
title: web (data-resources) migration
---

Recently, I was moving a couple of web portals (backed by Django) to another server. Because all web portals was developped to be transferable, many unexpected problems were encountered.

1. Soft links

   ```bash
   cp --remove-destination ./ ./
   ```

2. mixed absolut and relative file path

3. Implicit required R packages

   Instead of loading packages in the header, some functions were loaded using "::"

4. Function signature changed

   ```R
   readr::read_rds(path=) #deprecated
   
   read::read_rds(file=)  #current signature
   ```

5. admin keyword blocked 

   My organization blocked any requests containing admin keyword (403 forbidden). Thus, some static files, such as sb-admin.js, could be loaded. These have to be replaced or renamed.

