# Merge Sort
**TIME COMPLEXITY: O(N * LogN)**

this algorithm is a kind of divide and conquer and it contains of **Dividing** and **Sorting** sub arrays.

consider we have an array like below:

| 20 | 35 | -15 |7 | 55 | 1 | -22| 
|---|---|---|---|---|---|---|

<br></br>
Now we want to sort it in ascending order.

```
FIND a MIDPOINT for the array
DIVIDE array from MIDPOINT RECURSIVELY

SORT DIVIDED sub-arrays RECURSIVELY

MERGE sub-arrays RECURSIVELY

```

# Sample Code

```java
// mergeSort function
public static void mergeSort(int[] arr, int start, int end) {
    int midPoint = (end + start) / 2;
    if (end - start < 2) {
        return;
    }

    //left
    mergeSort(arr, start, midPoint);

    //right
    mergeSort(arr, midPoint, end);

    merge(arr, start, midPoint, end);
}



// merge function
public static void  merge(int[] arr, int start, int mid, int end) {
    int i = start;
    int j = mid;
    int tempIndex = 0;
    int[] tempArr = new int[arr.length];

    while (i < mid && j < end) {
        tempArr[tempIndex++] = arr[i] <= arr[j] ? arr[i++] : arr[j++];
    }

    while (i < mid) {
        tempArr[tempIndex ++] = arr[i++];
    }

    while (j < mid) {
        tempArr[tempIndex ++] = arr[j++];
    }

    System.arraycopy(tempArr, 0, arr, start, tempIndex);
}

// final array => {-55, -10, 1, 10, 20, 35, 55}

```

