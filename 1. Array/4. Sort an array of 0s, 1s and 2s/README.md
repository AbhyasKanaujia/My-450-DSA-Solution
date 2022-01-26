# Sort an array of 0s, 1s and 2s

> Given an array of size N containing only 0s, 1s, and 2s; sort the array in ascending order.

```plaintext
Input:
  N = 5
  arr[]= {0 2 1 2 0}
Output:
  0 0 1 2 2
Explanation:
  0s 1s and 2s are segregated into ascending order.
```

Expected Time Complexity: $O(N)$

Expected Auxiliary Space: $O(1)$

Constraints:

- $1 \le N \le 10^6$
- $0 \le A[i] \le 2$

[Link](https://practice.geeksforgeeks.org/problems/sort-an-array-of-0s-1s-and-2s/1)

Source: GFG

Difficulty: Easy

## Using sorting

1. Sort the array

Time Complexity: $O(N \log N)$ ❌

Space Complexity: $O(1)$ ✅

## Count and build array

1. Count number of 0s and 1s
2. Fill 0s from beginning till `n(0)`
3. Fill 1s from count of 0s till `n(0) + n(1)`
4. Fill rest with 2s from `n(0) + n(1)` till end

```cpp
void sort012(int a[], int n)
{
    int zeros = 0, ones = 0;
    for(int i = 0; i < n; i++)
        if(a[i] == 0)
            zeros++;
        else if(a[i] == 1)
            ones++;

    for(int i = 0; i < zeros; i++)
        a[i] = 0;
    for(int i = zeros; i < zeros + ones; i++)
        a[i] = 1;
    for(int i = zeros + ones; i < n; i++)
        a[i] = 2;
}
```

Time Complexity: $O(N)$ ✅

Space Complexity: $O(1)$ ✅

## Three Pointer Approach

Maintain three pointers `i`, `j`, `k`. Such that

1. `i` points next to all 0s from left
2. `j` points next to all 1s from left
3. `k` points before all 2s from right

```cpp
void sort012(int a[], int n)
{
    int i = 0, j = 0, k = n - 1;
    while(j <= k)
        switch(a[j]) {
        case 0:
            swap(a[i++], a[j++]);
            break;
        case 1:
            j++;
            break;
        case 2:
            swap(a[j], a[k--]);
            break;
        }
}
```

Time Complexity: $O(N)$ ✅

Space Complexity: $O(1)$ ✅
