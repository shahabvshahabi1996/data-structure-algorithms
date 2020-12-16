# Quick Sort
**TIME COMPLEXITY: O(N * LogN)**

this algorithm is a kind of divide and conquer and it contains of **Dividing** and **Sorting** sub arrays.and has two parts of partitioning and sorting.

consider we have an array like below:

| 20 | 35 | -15 |7 | 55 | 1 | -22| 
|---|---|---|---|---|---|---|

<br></br>
Now we want to sort it in ascending order.

```
FIND a PIVOT for the array

PUT all elements SMALLER than PIVOT to left
PUT all elements BIGGER than PIVOT to right

MERGE sub-arrays RECURSIVELY

```
# Sample Code

```java
// quickSort function
public static void quickSort(int[] arr, int start, int end) {
    if (end - start < 2) {
        return;
    }

    int pivotIndex = partition(arr, start, end);

    // left
    quickSort(arr, start, pivotIndex);
    // right
    quickSort(arr, pivotIndex + 1, end);

}

// partition function
public static int partition(int [] arr, int start, int end) {
    int pivot = arr[start];
    int i = start;
    int j = end;

    while (i < j) {
        // empty loop
        while (i < j && arr[--j] >= pivot);
        if (i < j) {
            arr[i] = arr[j];
        }
        
        // empty loop
        while (i < j && arr[++i] <= pivot);
        if (i < j) {
            arr[j] = arr[i];
        }
    }

    arr[i] = pivot;

    return j;
}

// final array => {-55, -10, 1, 10, 20, 35, 55}

```

