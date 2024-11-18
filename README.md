# Mergesort

Implement an iterative (no recursive calls) and in-place version of mergesort.
Use the template I've provided in `code.js`. Test your new function; I've
provided some basic testing code that uses
[jsverify](https://jsverify.github.io/) in `code.test.js`.

Hint: To make merge sort in-place, think about what happens during the merge --
where are elements moved to and from? To make it iterative, think about the
part of the array each recursive call considers.

## Runtime Analysis

Analyse the time complexity of your implementation and give a $\Theta$ bound for
its worst-case runtime. Add your answer, including your reasoning, to this
markdown file.

### Time complexity and Worst case runtime 

Outer Loop doubles the subarray width, starting at 1 and increases as 2^k until the width goes past n which is the size of the array. 

Total iterations = log<sub>2</sub>n

Inner loop processes the subarrays of size width within each iteration of the outer loop. Each subarray is merged with a step size of 2 x width which means you'd need O(n/width) iterations in the worst case.

Merge iterates over both the left and right subarrays which have 2 x width elements when together because both left and right are of size width. The shifting operations takes O(width) in the worst case as it shifts elements to insert one misplaced elements. 
Together this makes merge O(width^2) in the worst case.

Overall, if the inner loop runs O(n/width) and merge takes O(width^2) then

```
 O((n/width) * width^2) = O(n * width)
```

Summing the overall width = 1 + 2 + 4 + n = O(n)

Total Time = $O(n * n)$

Worst case is $\Theta(n^2)$ mostly due to the shifting of elements in merge. If merge were implemented better, the time complexity could be reduced to O(n logn)

## Plagiarism Acknowledgement

I read (this geeks for geeks page)[https://www.geeksforgeeks.org/in-place-merge-sort/#] to look at different approaches to in-place merge sort

I also used Chatgpt to help me understand how to treat width in merge for the runtime analysis

"I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice."
