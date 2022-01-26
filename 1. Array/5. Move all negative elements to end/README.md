# Move all negative elements to end

> Given an unsorted array `arr[]` of size `N` having both negative and positive integers. The task is place all negative element at the end of array without changing the order of positive element and negative element.

```plaintext
Input :
  N = 8
  arr[] = {1, -1, 3, 2, -7, -5, 11, 6 }
Output :
  1  3  2  11  6  -1  -7  -5
```

Expected Time Complexity: <!-- $O(N)$ --> <img style="transform: translateY(0.1em); filter: invert();" src="https://render.githubusercontent.com/render/math?math=O(N)"> ✅

Expected Auxiliary Space: <!-- $O(N)$ --> <img style="transform: translateY(0.1em); filter: invert();" src="https://render.githubusercontent.com/render/math?math=O(N)"> ✅

[Link](https://practice.geeksforgeeks.org/problems/move-all-negative-elements-to-end1813/1)

Source: GFG

Difficulty: Easy

## Two arrays

1. Positive = [], Negative = []
2. Traverse arr
   1. if negative, push to Negative
   2. else, push to Positive
3. Traverse Positive
   1. push to arr
4. Traverse Negative
   1. push to arr

```cpp
void segregateElements(int arr[],int n) {
    vector<int> positive, negative;
    for(int i = 0; i < n; i++)
        if(arr[i] < 0)
            negative.push_back(arr[i]);
        else
            positive.push_back(arr[i]);

    int i = 0;
    for(int x: positive)
        arr[i++] = x;
    for(int x: negative)
        arr[i++] = x;
}

```

Time Complexity: <!-- $O(N)$ --> <img style="transform: translateY(0.1em); filter: invert();" src="https://render.githubusercontent.com/render/math?math=O(N)"> ✅

Space Complexity: <!-- $O(N)$ --> <img style="transform: translateY(0.1em); filter: invert();" src="https://render.githubusercontent.com/render/math?math=O(N)"> ✅

## Failed Attempts

### Two Pointers ❌

1. `i = 0, j = n - 1`
2. While `i < j`
   1. `i++` until `arr[i] >= 0`
   2. `j--` until `arr[j] <= 0`
   3. Swap `arr[i]` and `arr[j]`

Time Complexity: <!-- $O(N)$ --> <img style="transform: translateY(0.1em); filter: invert();" src="https://render.githubusercontent.com/render/math?math=O(N)">

Space Complexity: <!-- $O(1)$ --> <img style="transform: translateY(0.1em); filter: invert();" src="https://render.githubusercontent.com/render/math?math=O(1)">

#### Reason for Failure

Since we are swapping elements, we are changing the order of elements.
