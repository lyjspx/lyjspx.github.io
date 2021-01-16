---
title: R objects and subsetting
tags:
- ''
- R
---

source [Adcanced R ](http://adv-r.had.co.nz)

## Four OO systems
1. Base object
2. S3
3. S4
4. Reference classes

### **Base object**
Underlying every R object is a C structure (or struct) that describes how that object is stored in memory. 

### **S3 object**
In S3, methods belong to functions, called generic functions, or generics for short. S3 methods do not belong to objects or classes.

S3 objects are usually built on top of lists, or atomic vectors with attributes. 

### **S4 object**
 
S4 works in a similar way to S3, but it adds formality and rigour. Methods still belong to functions, not classes.

Inheritence supported.
Method dispatch can be based on multiple arguments to a generic function, not just one.
There is a special operator, @, for extracting slots (aka fields) from an S4 object.

### **Referenece class**

Reference classes (or RC for short) are the newest OO system in R
RC methods belong to objects, not functions
RC objects are mutable: the usual R** *copy-on-modify semantics do not apply* **

---
Note: 

#### S3 objects
S3 objects are made up of atomic vectors, arrays, and lists, so you can always pull apart an S3 object using the techniques described above and the knowledge you gain from str().

DataFrame is built based on List!


### #S4 objects
There are also two additional subsetting operators that are needed for S4 objects: @ (equivalent to $), and slot() (equivalent to [[). @ is more restrictive than $ in that it will return an error if the slot does not exist. These are described in more detail in the OO field guide.

$ is a shorthand operator, where x$y is equivalent to x[["y", exact = FALSE]]

---
# Conclusion
Now, R is more like a modern language. However, few people will use it for OOP. People will stick to its original base and S3 objects.
