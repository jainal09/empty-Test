# empty-Test

Search Algorithms — Binary Search Code Implementation and Complexity Analysis It is crucial for developers to comprehend the concept of search algorithms, which utilize a step-by-step approach to locate specific data in a collection. This article will delve into the implementation of search algorithms in Java and Python, providing insights into their operation. Search algorithms are designed to retrieve or verify an element in any data structure in which it is stored, searching for a target (key) in the search space.

AI Generated Binary Search Images povered by DallE A search algorithm is an algorithm that solves the problem of finding and retrieving information stored in a data structure, or calculated in the search space of a problem domain, either with discrete or continuous values. Search algorithms are intended to retrieve or check an element in any data structure where it is stored, and they search for a target (key) in the search space.

This post will focus on Binary Search. We will discuss these two types of search algorithms in detail, including examples, code implementations, and time complexity analysis

Binary Search is an efficient algorithm used to find the position of a specific value within a sorted array. It follows the divide and conquer principle, making it one of the fastest searching algorithms.

Let’s consider a sorted array as an example and understand how Binary Search works: Suppose we have an array:

arr = \[2, 12, 15, 17, 27, 29, 45] and we want to find the position of the target element 17.

binary\_search(array, target): left = 0 right = length(array) - 1

```
while left <= right:
    mid = (left + right) / 2
    if array[mid] == target:
        return mid
    elif array[mid] < target:
        left = mid + 1
    else:
        right = mid - 1

return -1
```

The above is a pseudo code approach for Binary Search involving the following steps:

1. Compare the target element with the middle element of the sorted array.
2. If the target element is greater than the middle element, the search continues in the right half of the array.
3. If the target element is less than the middle element, the search continues in the left half of the array.
4. The above steps are repeated until the middle element is equal to the target element or the target element is not in the array.
5. If the target element is found, its index is returned. Otherwise, -1 is returned to indicate that the target element is not in the array.

Code Implementation Here is an implementation of Binary Search in Java:

Search.java In this implementation, we first define an array of integers and the target element we want to search. We then call the search method and pass the array and target as parameters.

The search method implements the Binary Search algorithm. It initializes the start and end indices of the array, and then enters a loop that continues until the start index is less than or equal to the end index.

In each iteration of the loop, we calculate the middle index of the array using (start + end) / 2. We then compare the target element with the middle element of the array. If the middle element is greater than the target, we discard the right half of the array by setting the end index to mid - 1. If the middle element is less than the target, we discard the left half of the array by setting the start index to mid + 1. If the middle element is equal to the target, we return its index.

If the target element is not found in the array, we return -1 to indicate that it is not present.

Binary Search in Python

search.py The provided code is a Python implementation of the binary search algorithm. The search function takes in an array of numbers nums and a target value target, and returns the index of the target in the array. The function first initializes start and end variables to the start and end indices of the array, respectively. It then uses a while loop to repeatedly divide the search space in half until it either finds the target value or determines that the target is not in the array. The midpoint index is calculated using (start+end)//2. If the target is less than the midpoint value, the search continues on the left half of the array by setting end to mid-1. If the target is greater than the midpoint value, the search continues on the right half of the array by setting start to mid+1. If the target is equal to the midpoint value, the function returns the midpoint index. If the loop finishes without finding the target, the function returns -1. The provided code is well-structured and uses clear variable names, making it easy to understand and modify as needed.

Time Complexity Analysis The time complexity of Binary Search can be analyzed based on the Best Case, Average Case, and Worst Case scenarios.

In the Best Case, the target element is the middle element of the array, and the time complexity is O(1) as only one comparison is required.

On average, the target element is somewhere in the array, resulting in a time complexity of O(logN).

In the Worst Case, the target element is not in the list or away from the middle element, which results in a time complexity of O(logN).

To calculate the time complexity of Binary Search, we can count the number of iterations k until the iteration terminates. At each iteration, the array is divided in half, and the length of the array at any given iteration is N.

The iteration starts at 1, and the number of iterations is k.

Length of array = N At Iteration 2,

Length of array = N/2 At Iteration 3,

Length of array = N/2^k To analyze the time complexity of binary search, we consider three cases: best case, average case, and worst case. In the best case, the target element is the middle element of the array, and only one comparison is required. Hence, the time complexity is O(1). In the average case, the target element is somewhere in the array, and the time complexity is O(logN), where N is the length of the array. In the worst case, the target element is not in the list or it is far away from the middle element, and the time complexity is also O(logN).

To calculate the time complexity of binary search, we assume that the iteration terminates after k iterations. At each iteration, the length of the array is divided by half. After k divisions, the length of the array becomes 1, and hence N = 2^k. By taking the log function of both sides, we get k = log2(N). Therefore, the time complexity of binary search is log2(N).

We can visualize this entire algorithm with the awesome tool by University of San Francisco. Below is a gif of the visualization made using this tool

Order Agnostic Binary Search Here’s an explanation of the Order-agnostic Binary Search algorithm. It’s used to find a target element in a sorted array, where we don’t know if the array is sorted in ascending or descending order. The approach is similar to the standard binary search algorithm, but first, we need to determine if the array is sorted in ascending or descending order. Once we know that, we can proceed with the search.

To start, we compare the target with the middle element of the array. If the array is sorted in ascending order and the target is less than the middle element, or if the array is sorted in descending order and the target is greater than the middle element, we continue the search in the lower half of the array by setting end=mid-1. Otherwise, we perform the search in the upper half of the array by setting start=mid+1.

To determine whether the array is sorted in ascending or descending order, we compare the first and last elements of the array. This lets us make the decision about whether to continue the search in the left half or the right half of the array.

Code Implementation Implementation in Java

OrderAgnosticSearch.java This code demonstrates an implementation of the Order-Agnostic Binary Search algorithm. This algorithm is used to find the index of a target element in a sorted array, regardless of whether the array is sorted in ascending or descending order.

The code first defines two example arrays nums1 and nums2 and a target element target. It then prints the result of calling the search function on both arrays with the target element as an argument.

The search function takes an integer array arr and the target integer target as input. It initializes start and end pointers to the first and last indices of the array, respectively. It then checks whether the array is sorted in ascending order by comparing the first and last elements of the array.

Inside the while loop, it calculates the middle index mid of the array using the binary search approach. If the target element is found at the middle index, it returns the index mid. Otherwise, it checks whether the array is sorted in ascending or descending order, and whether the target element is less than or greater than the middle element. Based on these conditions, it either searches in the lower half or upper half of the array by updating start and end pointers.

If the target element is not found in the array, the function returns -1.

Implementation in Python

This code defines a function search\_array that takes an array and a target value and performs a binary search on the array to find the target value. The array can be either in ascending or descending order. The function returns the index of the target value in the array, or -1 if the target value is not found.

The function starts by setting the start and end indices of the search range, and determines whether the array is in ascending or descending order based on the values of the first and last elements. It then enters a while loop that continues until the start index is greater than the end index. In each iteration of the loop, it calculates the midpoint index and checks whether the target value is at that index. If it is, the function returns the index.

If the target value is not at the midpoint index, the function checks whether the array is in ascending or descending order, and adjusts the start or end index accordingly. This continues until the target value is found or until the start index becomes greater than the end index, in which case the function returns -1.

Finally, the code defines two arrays and a target value, and calls the search\_array function on each array with the target value. The results of the searches are printed to the console.

Time Complexity Analysis There will be no change in the time complexity, so it will be the same as Binary Search.

Application of Binary Search in Real Word Use Cases

Images Generated by AI. Powered by DALLE Binary search is a highly efficient algorithm that finds numerous practical applications in real-life software development. It has several applications, some of which are:

Database Systems: Binary search is used in database systems to quickly find data records that match a specific query. Database indexes use binary search trees, which enables fast searches of the data. Sorting Algorithms: Binary search is used in sorting algorithms such as merge sort and quicksort to efficiently search for the correct position of elements in the array. Computer Games: Binary search is used in computer games to search for a specific item or enemy in a large map. Search Engines: Binary search is used in search engines to quickly find matching documents or web pages from a large database. Numerical Analysis: Binary search is used in numerical analysis to solve complex equations by iteratively refining the solution space. Compression Algorithms: Binary search is used in compression algorithms to search for the best encoding for a data stream. Operating Systems: Binary search is used in operating systems to search for files, locate memory blocks, and perform other low-level tasks. Binary search is a foundational algorithm in computer science, and its applications are ubiquitous in numerous software applications, making it a vital tool for every programmer to understand.

Conclusion In this article, we discussed binary search algorithm along with its code implementations in Python and Java. We also looked at the time complexity analysis.

Thanks for reading.

References:- This article is heavily inspired from the freecode camp article: Search Algorithms — Linear Search and Binary Search Code Implementation and Complexity Analysis by Ashutosh Krishna
