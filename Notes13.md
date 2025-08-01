# Introduction to Search (Binary & Linear)

### Defining Search
* Searching can determine 1 or both of 2 things
  *  If a particular value is in a ds (eg. a list)
  * Locate the position of that value in a list
* Two popular search algorithms
  * Linear Search
  * Binary Search

### Linear Search
* Also called **sequential search**
* Sequentially iterates over the array
  * Examines each element until it locates the value 
  * When value is found, returns index
  * If value !found, returns -1, indicating item not in list

### Linear Search Tradeoffs
* Benefits
  * Easy to understand
* Disadvantages
  * Inefficient (slow for a list with many elements)
* For *N* elements:
  * Best case: will find the element at the first index
  * Average case: will examine N/2 elements on average for a *value in the list*
  * Worse case: search N elements for the last value or if *value isn't in list*

### Question:
* There are 15 identical-looking coins; one of the coins is **counterfeit** and is known to be **lighter** than the genuine coins
* What is the **minimum number of weightings** needed to identify the fake coin with a two-pan balance scale without weights, like below
  * Weigh each coin against each other coin

### Slow Solutions:
* Sock-matching algorithm
  * Pull two socks from the laundry bag
  * If they match, pair them, if they don't return and repeat
* Compare each coin to each other coin(
  * Worst case - O(n^2)
* Compare two coins at a time
  * Worst case - T(n) = n/2 - O(n)

## Binary Search
1. Divide a *sorted* array into three sections
   * Middle element
   * Elements on one side of the middle element (low end) - **remember it's sorted in ascending order normally**
   * Elements on the other side of the middle element (high end)
2. If the middle element is the correct value, done
3. Else, repeat step 1 using only the half of the array that may contain the correct value
* Continue steps 1, 2, and 3 until either the value is found or there are no more elements to examine

### Binary Search Algorithm

```
set first to 0
set last to the last index in the array
set found to false
set position to -1
while found is not true and first is less than or equal to last
    // set middle to the index half-way between the indexes first and last
    set middle to (first + last) / 2
    if (array[middle] equals value
        set found to true
        set position to middle
    else if array[middle] is greater than the desired value
        set last to middle - 1 // search front half of the remaining values
    else
        set first to middle + 1 // search back half of the remaining values
    end if.
end while.
return position.
```

### Binary Search Tradeoffs
* Benefits
  * Much more efficient on *average* than linear search
* Disadvantages
  * It requires the list to be sorted, which is computationally expensive
  * Most sorting algorithms have typical cases of O(n*logn)
* For an array of N elements
  * Best case: performs 1 comparison // value is middle value
  * Average case: performs < log~2~(N) comparisons (log base 2 (n))
  * Worst case: performs at most log~2~(N) comparisons (log base 2 (n))
  * Even verifying sort order takes n comparisons