# Quicksort and big O
There are one primary reason to sort data - it makes it faster to find a specific element when the data is sorted.

The basic observation is that when the data is sorted, we can use what is called *binary search*.

Normally to see if an element is in a collection, we must first compare to the first element, then the next element, then the third element, then the forth element, etc. Thus you might need to search all the elements in the collection to see if the element is there. This is called **liniar search**.

If we know the elements are sorted, we can start by looking at the middle element and then see if the one we are looking at is in the left or right half. Then we look at the middle of the chosen half to determine in which quarter to look. We then look at the middle of the chosen quarter to find which eights it is in, until there is only one element left. This is called **binary search**

Binary search is very much faster than liniar. And one purpose of this note is to introduce **big O** as a way to compare such algorithms.

Just as liniar search slow compared to binary search, there are also big differences between a simple sorting algorithm and a fast one.

There are three fast ones which is typical to examine:

- Merge sort
- Heap sort
- Quick sort

We will look at Quicksort. The net is full of descriptions of all three of them - they are classic 1. year programming knowledge and have been in use and been thought for nearly 60 years. The build-in sorting in the Java libraries uses a quicksort algoritm.

## Readings:

### Quicksort
The basic algorithm is described here all over the net. [This one covers the important parts.](http://www.algolist.net/Algorithms/Sorting/Quicksort).

This page allow you to [run a quicksort animation](https://www.cs.usfca.edu/~galles/visualization/ComparisonSort.html) (and some other sorting algorithms).

### Exercise to be demoed:

Prepare a netbeans project which:

- Implements the quicksort algorithm so that it can sort Addresses (the simple class from last week) stored in an array list. Notice, you might need to extend the Address class with a compare method (depends on what you choose to do).
- can demo the project where it has a breakpoint when the algorithm is trying to partition one or less element.
- Has written test cases for 
	- a test which sorts an empty list
	- a test which sorts list of at least 10 elements
	- a test which sorts a list of at least 5 elements which are already sorted


### Big O
- [The rules of big-O are described in this page](https://www.interviewcake.com/article/java/big-o-notation-time-and-space-complexity)
- [The useage of logarithms are covered in this page](https://www.interviewcake.com/article/java/logarithms). The very short conclusion of that page is: "You can split N into halfs *log<sub>2</sub>(N)* times before you have only one left". We will return to why that is important.
- [Big O exercises](bigOexercises.md)

### Picking a datastruckture 
There is [this note comparing common operations](ChoosingACollection.md) of the buildin Java operations.
