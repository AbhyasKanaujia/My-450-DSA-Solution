# Find the Union and Intersection of the two sorted arrays.

> Given two arrays `a[]` and `b[]` of size `n` and `m` respectively. The task is to find union between these two arrays.
> Union of the two arrays can be defined as the set containing distinct elements from both the arrays. If there are repetitions, then only one occurrence of element should be printed in the union.

```plaintext
Input:
  5 3
  1 2 3 4 5
  1 2 3
Output: 
  5
Explanation: 
  1, 2, 3, 4 and 5 are the
  elements which comes in the union set
  of both arrays. So count is 5.
```

Expected Time Complexity : $O((n+m)\log(n+m))$

Expected Auxillary Space : $O(n+m)$

Constraints:

- $1 ≤ n, m ≤ 10^5$
- $0 ≤ a[i], b[i] < 10^5$

[Link](https://practice.geeksforgeeks.org/problems/kth-smallest-element5635/1)

Source: GFG

Difficulty: Medium

## Using Set

1. `set = {}`
2. Insert all elements of `a` to `set`
3. Insert all elements of `b` to `set`
4. `arr = [...set]`
5. return `arr[]`

