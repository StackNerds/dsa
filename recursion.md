# Recursion

- A recursive function is one that is defined in terms of itself (usually a simpler version). 
- A recursive function is function that calls itself.

When we call functions we expect them to return values, and so, if a function called ends up calling itself this would result in an infinite loop and the callback stack would overflow. For this reason, recursive functions must have a "stopping" condition known as a base-case.

## Illustration

### Factorial

The factorial (!) of a number is defined as follows:

```py
n! = n * (n-1)!, n >=1 and 1 when n == 0
```

The implementation in python looks like:

```py

def facto(n):
    if n == 0:
        return 0;
    return n * facto(n-1)
```

