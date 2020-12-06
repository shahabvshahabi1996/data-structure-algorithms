# Bubble Sort
**TIME COMPLEXITY: O(N^2)**

In this algorithm we are going to sort elements in array by swapping the elements with each other.
consider we have an array like below:

| 20 | 35 | -15 |7 | 55 | 1 | -22| 
|---|---|---|---|---|---|---|---|

<br></br>
Now we want to sort it in ascending order.

```
LOOP
start at index 0

if element at index i > element at index i + 1 
then swap element index i + 1 with index i.

if we rich the end element (array.length - 1)
then start at index 0.

END LOOP

repeat this LOOP about array.length - 2 times;

```

so the array will look like this:

## **Step 1**

first index = 0

second index = 1


| `20` | `35` | -15 |7 | 55 | 1 | -22| 
|---|---|---|---|---|---|---|---|

<br></br>

## **Step 2**

first index = 1

second index = 2

| 20 | `35` | `-15` |7 | 55 | 1 | -22| 
|---|---|---|---|---|---|---|---|
<br></br>

the array will look like this:

| 20 | `-15` | `35` |7 | 55 | 1 | -22| 
|---|---|---|---|---|---|---|---|

<br></br>

## **Step 3**

first index = 2

second index = 3

| 20 | -15 | `35` | `7` | 55 | 1 | -22| 
|---|---|---|---|---|---|---|---|
<br></br>
the array will look like this:

| 20 | -15 | `7`| `35` | 55 | 1 | -22| 
|---|---|---|---|---|---|---|---|
<br></br>

## **Step 4**

first index = 3

second index = 4

| 20 | -15 | 7 | `35` | `55` | 1 | -22| 
|---|---|---|---|---|---|---|---|

<br></br>

## **Step 5**
first index = 4

second index = 5

| 20 | -15 | 7 | 35 | `55` | `1` | -22| 
|---|---|---|---|---|---|---|---|
<br></br>
the array will look like this:

| 20 | -15 | 7 | 35 | `1` | `55` | -22| 
|---|---|---|---|---|---|---|---|
<br></br>

## **Step 6**
first index = 5

second index = 6

| 20 | -15 | 7 | 35 | 1 | `55` | `-22`| 
|---|---|---|---|---|---|---|---|
<br></br>
the array will look like this:

| 20 | -15 | 7 | 35 | 1 | `-22` | `55` | 
|---|---|---|---|---|---|---|---|
<br></br>

## Sample Code

```java

int[] array = {-55, 35, 20, 55, -10, 10, 1};

for (int lastUnsortedIndex = array.length - 1; lastUnsortedIndex > 0; lastUnsortedIndex --) {
            for (int index = 0; index < lastUnsortedIndex; index++) {
                if (array[index] > array[index + 1]) {
                    swapElements(array, index, index + 1);
                }
            }
        }

// final array => {-55, -10, 1, 10, 20, 35, 55}

```