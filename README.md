# Introduction to Sorting Algorithms using python

### What is Sorting 

Sorting is the process of arranging items systematically, and has two common, yet distinct meanings:

- Ordering: arranging items in a sequence ordered by some criterion;

- Categorizing: grouping items with similar properties

This repo contains implementation of sorting algorithms using the python programming language.

The sorting algorithms covered here include the following: 

 - Bubble Sort

 - Selection Sort

 - Insertion Sort

 - Merge Sort 

 - Quick Sort

### Bubble Sort

Bubble sort is based on theh idea of repeatedly comparing pairs of adjacent elements and then swapping their positions if they exist in the wrong order.

for Bubble sort, the elements goes through a series of iteration cycles till the elements are sorted. 

It is called Bubble sort because for each iteration, a bubble of maximum value is poped out. 

Given an array of N elements, Bubble Sort will:

    Compare a pair of adjacent items (a, b),
    Swap that pair if the items are out of order (in this case, when a > b),
    Repeat Step 1 and 2 until we reach the end of array
    (the last pair is the (N-2)-th and (N-1)-th items as we use 0-based indexing),
    By now, the largest item will be at the last position.
    We then reduce N by 1 and repeat Step 1 until we have N = 1
```
method bubbleSort(array A, integer N) // the standard version
  for each R from N-1 down to 1 // repeat for N-1 iterations
    for each index i in [0..R-1] // the 'unsorted region', O(N)
      if A[i] > A[i+1] // these two are not in non-decreasing order
        swap(a[i], a[i+1]) // swap them in O(1)
```
Comparison and swap require time that is bounded by a constant, let's call it c. Then, there are two nested loops in (the standard) Bubble Sort. The outer loop runs for exactly N-1 iterations. But the inner loop runs get shorter and shorter:

    When R=N-1, (N−1) iterations (of comparisons and possibly swaps),
    When R=N-2, (N−2) iterations,1

Bubble Sort is actually inefficient with its O(N^2) time complexity. Imagine that we have N = 105 numbers. Even if our computer is super fast and can compute 108 operations in 1 second, Bubble Sort will need about 100 seconds to complete.

However, it can be terminated early, e.g., on the small sorted ascending example shown above [3, 6, 11, 25, 39], Bubble Sort can terminates in O(N) time.

The improvement idea is simple: If we go through the inner loop with no swapping at all, it means that the array is already sorted and we can stop Bubble Sort at that point.

Discussion: Although it makes Bubble Sort runs faster in general cases, this improvement idea does not change O(N^2) time complexity of Bubble Sort... Why?
