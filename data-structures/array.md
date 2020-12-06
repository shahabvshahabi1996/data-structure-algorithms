# Arrays :
Time Complexity for any actions on the array.

<br></br>
|ACTION|TIME COMPLEXITY | DESCRIPTION |
|------|----------------|-------------|
|Access a data **WITH INDEX** | O(1) | Because we have the index and now we can simply retrive the data from our array.|
|Access a data **WITHOUT INDEX**| O(N) | Becasue for finding the index of an element inside the array we need to loop over the array for finding the index. |
|Add and element to a full array | O(N) | Because we need to copy the old array first and loop over the entire old array then need to add new element to new array with the length of oldArray.length + 1. | 
|Update element **WITH INDEX**| O(1) | Because we have the index. | 
|Delete element by setting it to `null`. **WITH INDEX**| O(1) | Because we have the index. | 
|Delete an element by shifting the entire array| O(N) | Becasue we need to loop array and shift the elements and put them into a new array.|