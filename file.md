# Program for Fibonacci numbers


The Fibonacci numbers are the numbers in the following integer sequence.
```

0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, ……..
```

In mathematical terms, the sequence Fn of Fibonacci numbers is defined by the recurrence relation
```
    Fn = Fn-1 + Fn-2
```
with seed values
```
   F0 = 0 and F1 = 1.
```
FOR nth Fibonacci -

Given a number n, print n-th Fibonacci Number.
Examples:
```
Input  : n = 2
Output : 1

Input  : n = 9
Output : 34
```

## Method 1 ( Use recursion ) 
A simple method that is a direct recursive implementation mathematical recurrence relation given above.

### Fibonacci Series using Recursion in java
```
class fibonacci 
{ 

    static int fib(int n) 

    { 

    if (n <= 1) 

       return n; 

    return fib(n-1) + fib(n-2); 

    } 

       

    public static void main (String args[]) 

    { 

    int n = 9; 

    System.out.println(fib(n)); 

    } 
}
```

## Output:
```
34
```
Time Complexity: T(n) = T(n-1) + T(n-2) which is exponential.
We can observe that this implementation does a lot of repeated work (see the following recursion tree). So this is a bad implementation for nth Fibonacci number.

                       fib(5)   
                     /                \
               fib(4)                fib(3)   
             /        \              /       \ 
         fib(3)      fib(2)         fib(2)   fib(1)
        /    \       /    \        /      \
  fib(2)   fib(1)  fib(1) fib(0) fib(1) fib(0)
  /     \
fib(1) fib(0)

## Method 2 ( Use Dynamic Programming )
We can avoid the repeated work done is method 1 by storing the Fibonacci numbers calculated so far.

### In java
```
class fibonacci 
{ 

   static int fib(int n) 

    { 

    /* Declare an array to store Fibonacci numbers. */

    int f[] = new int[n+2]; // 1 extra to handle case, n = 0 

    int i; 

       

    /* 0th and 1st number of the series are 0 and 1*/

    f[0] = 0; 

    f[1] = 1; 

      

    for (i = 2; i <= n; i++) 

    { 

       /* Add the previous 2 numbers in the series 

         and store it */

        f[i] = f[i-1] + f[i-2]; 

    } 

       

    return f[n]; 

    } 

       

    public static void main (String args[]) 

    { 

        int n = 9; 

        System.out.println(fib(n)); 

    } 
}
```
## Output:
```
34
```

Fibonacci Series up to n terms-

## In C

```
#include <stdio.h>
int main() {
    int i, n, t1 = 0, t2 = 1, nextTerm;
    printf("Enter the number of terms: ");
    scanf("%d", &n);
    printf("Fibonacci Series: ");

    for (i = 1; i <= n; ++i) {
        printf("%d, ", t1);
        nextTerm = t1 + t2;
        t1 = t2;
        t2 = nextTerm;
    }

    return 0;
}
```
