# euclids-algorithm
Implementation of Euclid's Algorithm for finding Greatest Common Divisor.

## What is
The Greatest Common Divisor, GCD, of two integers x and y that are both nonzero is the largest positive integer  
that is a factor of both x and y.  

GCD Theorem  
Let x and y be two positive integers.  Then  
GCD(x,y) = GCD(y mod x, x)  

Using the GCD Theorem, Euclid's Algorithm calls for repeatedly taking y mod x = r, replacing y with x and x with r, and then performing y mod x = r again until r = 0, in which case x is the GCD of the original x and y

## Pseudocode
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
