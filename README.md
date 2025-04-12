# euclids-algorithm
Implementation of Euclid's Algorithm for finding Greatest Common Divisor.
Implementation of Extended Euclidean Algorithm to express Greatest Common Divisor as a linear combination.

## What is
The Greatest Common Divisor, GCD, of two integers x and y that are both nonzero is the largest positive integer  
that is a factor of both x and y.  

GCD Theorem  
Let x and y be two positive integers.  Then  
GCD(x,y) = GCD(y mod x, x)  

Using the GCD Theorem, Euclid's Algorithm calls for repeatedly taking y mod x = r, replacing y with x and x with r, and then performing y mod x = r again until r = 0, in which case x is the GCD of the original x and y

#### Extended Euclidean Algorithm
A linear combination of x and y is sx + ty.  Using Euclid's algorithm, we can show that GCD(x,y) can be expressed in terms of sx + ty.

GCD(x,y) = sx + ty

The Extended Euclidean Algorithm requires us to perform the original algorithm for finding the GCD(x,y) using mod and saving the values of y,x,r at each iteration.  The second to the last iteration will render the GCD(x,y) and is the last time we will save values of y,x,r and will be the first values we plug into equation r = y - (y div x) * x.    

r = y - (y div x) * x is found using the definitions of the div and mod functions.  
mod function: r = y mod x  
div function: d = y div x  
div part2: y = dx + r  
r = y - dx  
r = y - (y div x) * x  

For each iteration descending from the original x,y to r = 0 but excluding the iteration of r = 0, put the values of y,x,r into the equation for each iteration.  Starting with the iteration directly above r = 0 (in which r is the GCD(x,y)), find a term in that equation that is equal to the r value in the superseding iteration, then substitute the value of the lower equation with the r equation of the superseding iteration.  Repeat up the iteration chain until you have the original x and y expressed with coefficients s and t and equal to the GCD(x,y) calculated at the next to last iteration.

## Pseudocode Original
Input: positive integers x and y  
Output: GCD(x,y)  
* if (y<x)
  * swap x and y
* r = y mod x
* while (r != 0)
    * y = x
    * x = r
    * r = y mod x
* return x

## Pseudocode Extended
Input: positive integer
