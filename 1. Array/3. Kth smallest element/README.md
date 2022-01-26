# Kth smallest element

study: [Heap](../../Study/1.%20Heap/)

> Given an array `arr[]` and an integer `K` where `K` is smaller than size of array, the task is to find the `K`th smallest element in the given array. It is given that all array elements are distinct.

```plaintext
Input:
  N = 6
  arr[] = 7 10 4 3 20 15
  K = 3
Output :
  7
Explanation :
  3rd smallest element in the given array is 7.
```

Expected Time Complexity: <!-- $O(n)$ --> <img style="transform: translateY(0.1em); filter: invert();" src="https://render.githubusercontent.com/render/math?math=O(n)">

Expected Auxiliary Space: <!-- $O(1)$ --> <img style="transform: translateY(0.1em); filter: invert();" src="https://render.githubusercontent.com/render/math?math=O(1)">

Constraints:

- <!-- $1 \le N \le 105$ --> <img style="transform: translateY(0.1em); filter: invert();" src="https://render.githubusercontent.com/render/math?math=1%20%5Cle%20N%20%5Cle%20105">
- <!-- $1 \le arr[i] \le 105$ --> <img style="transform: translateY(0.1em); filter: invert();" src="https://render.githubusercontent.com/render/math?math=1%20%5Cle%20arr%5Bi%5D%20%5Cle%20105">
- <!-- $1 \le K \le N$ --> <img style="transform: translateY(0.1em); filter: invert();" src="https://render.githubusercontent.com/render/math?math=1%20%5Cle%20K%20%5Cle%20N">

[Link](https://practice.geeksforgeeks.org/problems/kth-smallest-element5635/1)

Source: GFG

Difficulty: Medium

## Using Sorting

1. Sort
2. return kth element

```cpp
int kthSmallest(int arr[], int l, int r, int k) {
  sort(arr + l, arr + r + 1);
  return arr[l + k - 1];
}
```

Time Complexity: <!-- $O(n \log n)$ --> <img style="transform: translateY(0.1em); filter: invert();" src="https://render.githubusercontent.com/render/math?math=O(n%20%5Clog%20n)"> ❌

Space Complexity: <!-- $O(1)$ --> <img style="transform: translateY(0.1em); filter: invert();" src="https://render.githubusercontent.com/render/math?math=O(1)">

## Using Set

$\because\,$ it is given that all elements are distinct, we can use set to find the kth element.

1. Insert all elements in the set
2. Traverse the set k times
3. return the kth element

```cpp
int kthSmallest(int arr[], int l, int r, int k) {
  set<int> s(arr + l, arr + r - l + 1);
  auto it = s.begin();
  advance(it, k - 1);
  return *it;
}
```

Time Complexity: <!-- $O(log n)$ --> <img style="transform: translateY(0.1em); filter: invert();" src="https://render.githubusercontent.com/render/math?math=O(log%20n)"> in average case and <!-- $O(n)$ --> <img style="transform: translateY(0.1em); filter: invert();" src="https://render.githubusercontent.com/render/math?math=O(n)"> in worst case. ❌

Space Complexity: <!-- $O(n)$ --> <img style="transform: translateY(0.1em); filter: invert();" src="https://render.githubusercontent.com/render/math?math=O(n)"> ❌

## Using Min Heap

Deferred until I learn heap.
