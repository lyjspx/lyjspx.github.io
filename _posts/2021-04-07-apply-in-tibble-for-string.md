---
title: Apply in tibble (for String)
tags:
- R
---



When we apply some methods on tibble, there is an interesting but awkward setting.

For a column of character or String, tibble is not ware of the longest element of the column. Tibble will used  the first thousand elements to determine the column width. Then, a problem raises if the longest String occurs after first thousand elements. You will lose several characters.

