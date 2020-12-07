# Insertion Sort
**TIME COMPLEXITY: IT DEPENDS ON IMPLEMENTATION**

In this algorithm we are going to sort elements in array by shifting the elements and inserts the unsorted element to it's
correct position.

consider we have an array like below:

| 20 | 35 | -15 |7 | 55 | 1 | -22| 
|---|---|---|---|---|---|---|

<br></br>
Now we want to sort it in ascending order.

```
ASSIGN 1 to unSortedIndex

LOOP A
    ASSIGN unSortedIndex to index i

    LOOP B
        IF element i < element i - 1
        THEN swap element i and element i - 1 
    END B

    REPEAT B till i riches to 0 (first index)
END A

INCREASE unSortedIndex by 1 

REPEAT A till unSortedIndex riches the last index of array.

```

so the array will look like this:

## **Step 1**

unSortedIndex = 1

unSortedIndexElement = `35`

i = 0
 

| 20 | `35` | -15 |7 | 55 | 1 | -22| 
|---|---|---|---|---|---|---|

<br></br>

## **Step 2**

unSortedIndex = 2

unSortedIndexElement = `-15`

i = 1

| 20 | `35` | `-15` |7 | 55 | 1 | -22| 
|---|---|---|---|---|---|---|

<br></br>

checks that if unSortedIndexElement (`-15`) is less than element at index i (`35`) then it is going to shift the array to right.

| 20 | `-15` | `35` |7 | 55 | 1 | -22| 
|---|---|---|---|---|---|---|

<br></br>

unSortedIndex = 2

i = 0

checks that if unSortedIndexElement (`-15`) is less than element at index i (`20`) then it is going to shift the array to right.

the array will look like this:

| `-15` | `20` | `35` | 7 | 55 | 1 | -22| 
|---|---|---|---|---|---|---|

<br></br>

## **Step 3**

unSortedIndex = 3

unSortedIndex = `7`

i = 2

| -15 | 20 | 35 | `7` | 55 | 1 | -22| 
|---|---|---|---|---|---|---|

<br></br>

checks that if unSortedIndexElement (`7`) is less than element at index i (`35`) then it is going to shift the array to right.

| -15 | 20 | `7` | `35` | 55 | 1 | -22|  
|---|---|---|---|---|---|---|

<br></br>

i = 1

checks that if unSortedIndexElement (`7`) is less than element at index i (`20`) then it is going to shift the array to right.

| -15 | 20 | `7` | `35` | 55 | 1 | -22| 
|---|---|---|---|---|---|---|

<br></br>

i = 0

checks that if unSortedIndexElement (`7`) is less than element at index i (`-15`) then it is going to shift the array to right.

| -15 | `7` | `20` | `35` | 55 | 1 | -22| 
|---|---|---|---|---|---|---|

the array will look like this:

| -15 | `7` | `20` | `35` | 55 | 1 | -22| 
|---|---|---|---|---|---|---|

<br></br>

## **Step 4**

unSortedIndex = 4

unSortedIndexElement = `55`

i = 3

| -15 | 7 | 20 | 35 | `55` | 1 | -22| 
|---|---|---|---|---|---|---|

<br></br>

## **Step 5**

unSortedIndex = 5

unSortedIndexElement = `1`

i = 4

| -15 | 7 | 20 | 35 | 55 | `1` | -22| 
|---|---|---|---|---|---|---|

<br></br>

checks that if unSortedIndexElement (`1`) is less than element at index i (`55`) then it is going to shift the array to right.

| -15 | 7 | 20 | 35 | `1` | `55` | -22| 
|---|---|---|---|---|---|---|

<br></br>

i = 3

checks that if unSortedIndexElement (`1`) is less than element at index i (`35`) then it is going to shift the array to right.

| -15 | 7 | 20 | `35` | `1` | 55 | -22| 
|---|---|---|---|---|---|---|

<br></br>

i = 2

checks that if unSortedIndexElement (`1`) is less than element at index i (`20`) then it is going to shift the array to right.

| -15 | 7 | `20` | `1` | 35 | 55 | -22| 
|---|---|---|---|---|---|---|

<br></br>


i = 1

checks that if unSortedIndexElement (`1`) is less than element at index i (`7`) then it is going to shift the array to right.

| -15 | `7` | `1` | 20 | 35 | 55 | -22| 
|---|---|---|---|---|---|---|

<br></br>

i = 0

checks that if unSortedIndexElement (`1`) is less than element at index i (`-15`) then it is going to shift the array to right.

| `-15` | `1`| 7 | 20 | 35 | 55 | -22| 
|---|---|---|---|---|---|---|

the array will look like this:

| -15 | `1` | `7` | `20` | `35` | `55` | -22| 
|---|---|---|---|---|---|---|

<br></br>

## **Step 6**

unSortedIndex = 6

unSortedIndexElement = `-22`

i = 5

| -15 | 1 | 7 | 20 | 35 | 55 | `-22`| 
|---|---|---|---|---|---|---|

<br></br>

checks that if unSortedIndexElement (`-22`) is less than element at index i (`55`) then it is going to shift the array to right.

| -15 | 1 | 7 | 20 | 35 | `-22` | `55`|  
|---|---|---|---|---|---|---|

<br></br>

i = 4

checks that if unSortedIndexElement (`-22`) is less than element at index i (`35`) then it is going to shift the array to right.

| -15 | 1 | 7 | 20 | `35` | `-22` | 55|  
|---|---|---|---|---|---|---|

<br></br>

i = 3

checks that if unSortedIndexElement (`-22`) is less than element at index i (`20`) then it is going to shift the array to right.

| -15 | 1 | 7 | `20` | `-22` | 35 | 55|  
|---|---|---|---|---|---|---|

<br></br>

i = 2

checks that if unSortedIndexElement (`-22`) is less than element at index i (`7`) then it is going to shift the array to right.

| -15 | 1 | `7` | `-22` | 20 | 35 | 55|  
|---|---|---|---|---|---|---|

<br></br>

i = 1

checks that if unSortedIndexElement (`-22`) is less than element at index i (`1`) then it is going to shift the array to right.

| -15 | `1` | `-22` | 7 | 20 | 35 | 55|  
|---|---|---|---|---|---|---|

<br></br>

i = 0

checks that if unSortedIndexElement (`-22`) is less than element at index i (`-15`) then it is going to shift the array to right.

| `-15` | `-22` | 1 | 7 | 20 | 35 | 55|  
|---|---|---|---|---|---|---|

the array will look like this:

| `-22` | `-15` | `1` | `7`| `20` | `35` | `55`|  
|---|---|---|---|---|---|---|

<br></br>
## Sample Code

```java

int [] array = {-55, 35, 20, 55, -10, 10, 1};

for (int sortedIndex = 1; sortedIndex < array.length; sortedIndex ++ ) {
            for (int i = sortedIndex; i > 0; i --) {
                if(array[i] < array[i - 1]) {
                    swapElements(array, i, i - 1);
                }
            }
        }

// final array => {-55, -10, 1, 10, 20, 35, 55}
```


