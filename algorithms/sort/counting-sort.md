# Counting Sort
**TIME COMPLEXITY: O(N)**

this algorithm is good for **reasonable range of values** like 1 - 10 and we can use it for **whole values**.

consider we have an array like below:

| 2 | 5 | 7 |7 | 3 | 1 | 10| 
|---|---|---|---|---|---|---|

<br></br>
Now we want to sort it in ascending order.

```
MAKE COUNT_ARRAY with the length of max value in original array

COUNT the elements from the original array and put them in the right position of COUNT_ARRAY

MUTATE original array using COUNT_ARRAY and the numbers inside. 

```
## Convert array to Count array:

first we make a new array called `countArr` with length of `max` value of original array.

then we loop throw original array and count the numbers and place them in the right position of `countArr` and if have not any , we place `0`.

| 2 | 5 | 7 |7 | 3 | 1 | 10| 
|---|---|---|---|---|---|---|

<br></br>

we draw a table for more info:

| Value | How many values we have ? |
|-------|---------------------------|
|1  | 1 |
|2  | 1 |
|3  | 1 |
|4  | 0 |
|5  | 1 |
|6  | 0 |
|7  | 2 |
|8  | 0 |
|9  | 0 | 
|10 | 1 |



consider the original array and `countArr` will look like:

| 1 | 1 | 1 | 0 | 1 | 0 | 2 | 0 | 0 | 1 |
|---|---|---|---|---|---|---|---|---|---|



## Sample Code

```java

public static void countingSort(int[] arr, int max) {
    int[] countArr = new int[max];
    for (int i = 0; i < arr.length; i++) {
        countArr[arr[i] - 1]++;
    }
    // originalArr => { 2, 5, 7, 7, 3, 10 }
    // we have one 1s
    // one 2s
    // one 3s
    // one 5s
    // two 7s
    // one 10s
    // countArray => { 1, 1, 1, 0, 1, 0, 2, 0, 0, 1 }

    int j = 0;
    for (int i = 0; i < countArr.length; i++) {
        while (countArr[i] > 0) {
            countArr[i]--;
            arr[j++] = i + 1;
        }
    }

}

```