---
tags:
- computing
- numpy
- python
title: Numpy Vectorization using too much memory
---

# Numpy vectorization
Vectorization is a technique to accelerate computing.
[numpy vectorize v1.20](https://numpy.org/doc/stable/reference/generated/numpy.vectorize.html)
However, the data type of the output of vectorized is determined by calling the function with the first element of the input.

A thread in stackoverflow descripes this problem. Briefly, each value is evaluated as an object consuming much memory.
[How to avoid enormous additional memory consumption when using numpy vectorize?](https://stackoverflow.com/questions/7078371/how-to-avoid-enormous-additional-memory-consumption-when-using-numpy-vectorize)

I encountered this problems when I applied this techinque. It consumes all my memory (128GB). 
I tried to expand my swap to 256GB. The disk is not solid state, and thus the swap is pretty slow.
