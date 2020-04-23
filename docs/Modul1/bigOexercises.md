# Big O exercises
These exercises should be possible to solve using the two notes:

- [The rules of big-O are described in this page](https://www.interviewcake.com/article/java/big-o-notation-time-and-space-complexity)
- [The useage of logarithms are covered in this page](https://www.interviewcake.com/article/java/logarithms).

### Exercise 1What is the time growth rate (time complexity) of the following method?```javapublic static int count(int[] a, int c){  int count = 0;  for (int i = 0; i < a.length; i++)  {      if (a[i] == c) count++;  }    return count;  }```### Exercise 2Suppose an algorithm A takes 5 seconds to handle a dataset of 1000 elements. Fill in the approximate execution time for A depending on the complexity of the algorithm.N\big O   | O(n)|O(n<sup>2</sup>)|O(n<sup>3</sup>)
---|---|---|---1000 | 52000 |3000 |10000 |### Exercise 3For the following expressions, what is the order of growth (time complexity) of each?a)	n<sup>2</sup>+ 2n + 1b)	n<sup>10</sup> + 9n<sup>9</sup> + 20n<sup>8</sup> + 145n<sup>7</sup>c)	n + (0.001)n<sup>3</sup>d)	n + *log*(n)

### Exercise 4

Fill out a table where you compare n, log(n), n<sup>2</sup> and n*log(n) 

n | log(n) |n<sup>2</sup> | n*log(n)
---|---|---|---
10 | |
100 |
1000 |
5.700.000 (number of danes) |
7.400.000.000 (people in the world) |

