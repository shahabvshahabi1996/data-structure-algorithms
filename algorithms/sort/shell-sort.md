# Shell Sort
**TIME COMPLEXITY: IT DEPENDS ON IMPLEMENTATION || O(N^2)**

In this algorithm we are going to sort elements in array by shifting the elements and inserts the unsorted element to it's
correct position.
but it uses a gap, and the gap decrease by 1/2 in every step. 

consider we have an array like below:

| 20 | 35 | -15 |7 | 55 | 1 | -22| 
|---|---|---|---|---|---|---|

<br></br>
Now we want to sort it in ascending order.

```
ASSIGN (Array.length / 2) to GAP

LOOP A
    ASSIGN 0 to index i

    LOOP B
        IF element i > element i + GAP
        THEN swap element i with element i + GAP AND 
        IF element i < element i - GAP
        THEN swap element i with i - GAP

    END B

    REPEAT B till i + GAP < Array.length
END A

DECREASE GAP by 1 / 2 

REPEAT A till GAP riches 1.

```

so the array will look like this:

## **Step 1**

GAP = Array.length / 2 = 3

i = 0

j = i + GAP = 3

| `20` | 35 | -15 | `7` | 55 | 1 | -22| 
|---|---|---|---|---|---|---|

<br></br>

checks that if i element (`20`) is bigger than j element (`7`) then it will swap the elements. 

| `7` | 35 | -15 | `20` | 55 | 1 | -22| 
|---|---|---|---|---|---|---|

<br></br>
i = 1

j = i + GAP = 4

| 7 | `35` | -15 | 20 | `55` | 1 | -22| 
|---|---|---|---|---|---|---|

<br></br>

checks that if i element (`35`) is bigger than j element (`55`) then it will swap the elements. otherwise no changes will happen.

| 7 | `35` | -15 | 20 | `55` | 1 | -22| 
|---|---|---|---|---|---|---|

<br></br>
i = 2

j = i + GAP = 5

checks that if i element (`-15`) is bigger than j element (`1`) then it will swap the elements. otherwise no changes will happen.

the array will look like this:

| 7 | 35 | `-15` | 20 | 55 | `1`| -22| 
|---|---|---|---|---|---|---|

<br></br>
i = 3

j = i + GAP = 6

checks that if i element (`20`) is bigger than j element (`-15`) then it will swap the elements. otherwise no changes will happen.

| `7` | 35 | -15 | `-22` | 55 | 1| 20| 
|---|---|---|---|---|---|---|

now at this point it will check that if element i (`-22`)
is less than element i - GAP (`7`) then it will swap them.

the array will look like this:

| `-22` | 35 | -15 | `7` | 55 | 1| 20| 
|---|---|---|---|---|---|---|

<br></br>

## **Step 2**

GAP = GAP / 2 = 1

i = 0

j = i + GAP = 1

| -22 | 35 | -15 | 7 | 55 | 1| 20| 
|---|---|---|---|---|---|---|

<br></br>

checks that if i element (`-22`) is bigger than j element (`35`) then it will swap the elements. otherwise no changes will happen.

| `-22` | `35` | -15 | 7 | 55 | 1| 20| 
|---|---|---|---|---|---|---|

<br></br>
i = 1

j = i + GAP = 2

checks that if i element (`35`) is bigger than j element (`-15`) then it will swap the elements. otherwise no changes will happen.

| -22 | `-15` | `35` | 7 | 55 | 1| 20| 
|---|---|---|---|---|---|---|


<br></br>
i = 2

j = i + GAP = 3

| -22 | -15 | `35` | `7` | 55 | 1| 20| 
|---|---|---|---|---|---|---|

<br></br>

checks that if i element (`35`) is bigger than j element (`7`) then it will swap the elements. otherwise no changes will happen.

| -22 | -15 | `7` | `35` | 55 | 1| 20| 
|---|---|---|---|---|---|---|


<br></br>
i = 3

j = i + GAP = 4

| -22 | -15 | 7 | `35` | `55` | 1| 20| 
|---|---|---|---|---|---|---|

<br></br>

checks that if i element (`35`) is bigger than j element (`55`) then it will swap the elements. otherwise no changes will happen.

| -22 | -15 | 7 | `35` | `55` | 1| 20|
|---|---|---|---|---|---|---|

<br></br>
i = 4

j = i + GAP = 5

| -22 | -15 | 7 | 35 | `55` | `1`| 20|
|---|---|---|---|---|---|---|

<br></br>

checks that if i element (`55`) is bigger than j element (`1`) then it will swap the elements. otherwise no changes will happen.

| -22 | -15 | 7 | 35 | `1` | `55` | 20| 
|---|---|---|---|---|---|---|

now at this point it will check that if element i (`1`)
is less than element i - GAP (`35`) then it will swap them.

and we keep continue this steps till we find the right position for element `1`

the array will look like this:

| -22 | -15 | `1` | `7` | `35` | `55` | 20| 
|---|---|---|---|---|---|---|

<br></br>
i = 5 

j = i + GAP = 6

| -22 | -15 | 1 | 7 | 35 | `55` | `20`| 
|---|---|---|---|---|---|---|

<br></br>

checks that if i element (`55`) is bigger than j element (`20`) then it will swap the elements. otherwise no changes will happen.

| -22 | -15 | 1 | 7 | 35 | `20` | `55`| 
|---|---|---|---|---|---|---|

now at this point it will check that if element i (`20`)
is less than element i - GAP (`35`) then it will swap them

and we keep continue this steps till we find the right position for element `20`

the array will look like this:

| `-22`| `-15` | `1` | `7` | `20` |  `35` | `55` |
|---|---|---|---|---|---|---|

<br></br>


## Sample Code

```java

int [] array = {-55, 35, 20, 55, -10, 10, 1};

for (int gap = array.length / 2; gap > 0; gap /= 2) {
            for (int i = 0; i + gap < array.length; i ++) {
                if (array[i] > array[i + gap]) {
                    swapElements(array, i, i + gap);
                    if (i - gap >= 0 && array[i - gap] > array[i]) {
                        swapElements(array, i - gap, i);
                    }
                }
            }
        }

// final array => {-55, -10, 1, 10, 20, 35, 55}
```


