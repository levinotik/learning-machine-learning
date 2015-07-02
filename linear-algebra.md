# Linear Algebra

## Matrices
[crash course](https://www.youtube.com/watch?v=6AP4IvfKmwg&list=PLnnr1O8OWc6boN4WHeuisJWmeQHH9D_Vg)

A **matrix** is a rectangular array of numbers. 

Example

```
--------- 
| 1   8 |
| 3   7 |
| 9   2 |
---------
```

The dimension of a matrix is the `number of rows X the number of columns`. The above matrix has dimension `2 X 3`.

The notation `ℝ³ˣ²` means that this matrix is an element of the set `ℝ³ˣ²`, or "the set of all matrices with dimension `ℝ³ˣ²`"

### Matrix elements

`A𝑖𝚓` means "i, j entry" in the ith row and jth column. so `A₁₁` = `1` in our example and `A₃₂` = `2` in our example. 

## Vectors

A **vector** is just a special case of matrix, namely an `n x 1` matrix or n rows, 1 column. 

```
    -----
    | 1 |
y = | 3 | 
    | 9 |
    -----
```

`y` is also called a `3-dimensional vector`, meaning a vector with 3 elements. Or a vector in the set `ℝ³` which is the set of all 3-dimensional vectors. 

### Vector elements

`Y𝑖` = `𝑖ᵗʰ` element

y1 = 1 and y3 = 9 in our example. Sometimes 1-indexed is used and sometimes 0-indexed. Programmers are probably used to 0-indexed. In math 1-indexed more common, but 0-indexed more convenient notation in ML specifically. 

# Conventions

uppercase letters `A, B, C, X` refer to matrices. 

lowercase letters, `a, b, x, y` refer to vectors. 

# Matrix addition and subtraction

adding two matrices results in another matrix. To add, just add each corresponding element from the matrices. You can only add matrices if they have the same dimension. 


```
--------- 
| 1   8 |    
| 3   7 | 
| 9   2 |
---------

	+
	
--------- 
| 1   8 |
| 3   7 | 
| 9   2 |
---------

   =
  
----------- 
|  2   16 |
|  6   14 | 
| 18    4 |
----------- 
   
```

Subtraction works the same way.

# Scalar multiplication

**scalar** is a fancy word for "just plain a number"

```
	 ---------     ----------
	 | 1   8 |     |  3  24 |
3 x	 | 3   7 |  =  |  9  21 |
	 | 9   2 |     | 27   6 |
	 ---------     ----------
```

Just take each element and multiply it by 3, one at a time.


### Division

```
--------  			 
| 4  0 |  /4     
| 6  3 | 			    
--------  
	=
	
	
	--------  			 
	| 4  0 |  
1/4 | 6  3 | 			    
	-------- 
           
```

### combining operands

![screenshot](http://take.ms/mMK9W)


# matrix vector multiplication

![screenshot](http://take.ms/wAbwt)

**number of columns in matrix must match number of rows in vector**

To multipliy a matrix with dimension m x n by a n x 1 matrix, the `n's` must be the same. We can multiply, for example, a matrix 2 x 3 by a vector 3 x 1, but not one that is 2 x 3 by a vector 4 x 1.

the product will be an `m` dimensional vector. 

the multiplication proceeds by multiplying ever column in A by every row in x and add them up.



