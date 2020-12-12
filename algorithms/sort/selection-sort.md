# Selection Sort
**TIME COMPLEXITY: O(N^2)**

In **Selection Sort** just like the [bubble sort](./bubble-sort.md), this algorithm uses swap method but with a difference.
difference is you swap when second element is bigger that first one.

<br></br>
consider we have an array like below:

| 20 | 35 | -15 |7 | 55 | 1 | -22|
|----|----|-----|--|----|---|----|


Now we want to sort it in ascending order.
just like below:

```
LOOP
largest index = 0

if element at index i < element at index j 
then we put largest to index = j.

if we rich the last unsorted index then we swap the largest index
element with the last unsorted index.

start at index 0.
END LOOP

repeat this LOOP till we get the sorted array
```
<br></br>
The execution table this array will look like this:

|20 | 35|-15| 7 | 55| 1 | -22| 
|---|---|---|---|---|---|----|

<br></br>
## **Step 1**

|elementIndex | largestIndex | lastUnSortedIndex |
|-------------|--------------|-------------------|
|0|0|6|
|1|1|6|
|2|1|6|
|3|1|6|
|4|4|6|
|5|4|6|
|6|`4`|`6`|

    we swap the element index = 4 with index = 6

the result will look like this:

|20 | 35 |-15|7  | -22| 1 | `55`| 
|---|----|---|---|----|---|-----|

<br></br>

## **Step 2**

|elementIndex | largestIndex | lastUnSortedIndex |
|-------------|--------------|-------------------|
|0|0|5|
|1|1|5|
|2|1|5|
|3|1|5|
|4|1|5|
|5|`1`|`5`|

    we swap the element index = 1 with index = 5

the result will look like this:

|20 | 1 | -15 |7 | -22 | `35` | `55`| 
|---|---|---|---|---|---|---|

<br></br>

## **Step 3**

|elementIndex | largestIndex | lastUnSortedIndex |
|-------------|--------------|-------------------|
|0|0|4|
|1|0|4|
|2|0|4|
|3|0|4|
|4|`0`|`4`|

    we swap the element index = 0 with index = 4

the result will look like this:

|-22 | 1 | -15 | 7 | `20` | `35` | `55`| 
|---|---|---|---|---|---|---|

<br></br>

## **Step 4**

|elementIndex | largestIndex | lastUnSortedIndex |
|-------------|--------------|-------------------|
|0|0|3|
|1|1|3|
|2|1|3|
|3|`3`|`3`|

    we swap the element index = 3 with index = 3

the result will look like this:

|-22 | 1 | -15 | `7` | `20` | `35` | `55`| 
|---|---|---|---|---|---|---|

<br></br>


## **Step 5**

|elementIndex | largestIndex | lastUnSortedIndex |
|-------------|--------------|-------------------|
|0|0|2|
|1|1|2|
|2|`1`|`2`|

    we swap the element index = 1 with index = 2

the result will look like this:

|-22 | -15 | `1` | `7` | `20` | `35` | `55`| 
|---|---|---|---|---|---|---|

<br></br>


## **Step 6**

|elementIndex | largestIndex | lastUnSortedIndex |
|-------------|--------------|-------------------|
|0|0|1|
|1|`1`|`1`|

    we swap the element index = 1 with index = 1

the result will look like this:

|-22 | `-15` | `1` | `7` | `20` | `35` | `55`| 
|---|---|---|---|---|---|---|

<br></br>

## **Step 7**

|elementIndex | largestIndex | lastUnSortedIndex |
|-------------|--------------|-------------------|
|0|`0`|`0`|

    we swap the element index = 0 with index = 0

the result will look like this:

|`-22` | `-15` | `1` | `7` | `20` | `35` | `55`| 
|---|---|---|---|---|---|---|

<br></br>
## Sample Code

```java

int [] array = {-55, 35, 20, 55, -10, 10, 1};

for (int lastUnsortedIndex = array.length - 1; lastUnsortedIndex > 0; lastUnsortedIndex --) {
            int largestIndex = 0;
            for (int index = 0; index <= lastUnsortedIndex; index++) {
                if(array[index] > array[largestIndex]) {
                    largestIndex = index;
                }
            }
            swapElements(array, lastUnsortedIndex, largestIndex);
        }

// final array => {-55, -10, 1, 10, 20, 35, 55}
```
