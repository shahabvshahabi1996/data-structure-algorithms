# Recursion

happens when a function being defined is applied within its own definition. 

for example we can make factorial function, both in recursion and normal like so:

## Normal

```java

void factorial(int n) {
    int result = 1;
    for(int i = n; i > 0; i++) {
        result = n * result;
    }
}


// result for 3 would be => 3 * 2 * 1 = 6
```

## Recursion

**NOTE**
if you don't stop the function execution with a condition it will go till get stack overflow error.


```java
int factorial(int n) {
    if (n == 1) {
        return 1;
    }

    return n * factorial(n - 1);
}

// result for 3 would be => 3 * 2 * 1 = 6

```