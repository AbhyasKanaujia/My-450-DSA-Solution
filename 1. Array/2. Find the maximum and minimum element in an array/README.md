# Find the maximum and minimum element in an array

> Write a C function to return minimum and maximum in an array. Your program should make the minimum number of comparisons.

[link](https://www.geeksforgeeks.org/maximum-and-minimum-in-an-array/)
Level: Basic
Source: GFG

## Linear Search

1. `min = arr[0]`, `max = arr[0]`
2. Traverse the array from `1` to `n-1`
   1. If `arr[i] < min`, then `min = arr[i]`
   2. If `arr[i] > max`, then `max = arr[i]`

```cpp
struct MinMax{
    int min, max;
};
MinMax findMinMax(int arr[], int n){
  MinMax m;
  m.min = INT_MAX;
  m.max = INT_MIN;
  for(int i = 0; i < n; i++){
    if(arr[i] < m.min)
      m.min = arr[i];
    if(arr[i] > m.max)
      m.max = arr[i];
  }
  return m;
}
```

Time Complexity: $O(n)$
Space Complexity: $O(1)$
Number of comparisons: $n$

## Tournament Selection

```cpp
struct MinMax{
    int min, max;
};
MinMax findMinMax(int arr[], int low, int high) {
  int n = high - low + 1;
  MinMax m;
  if(n == 1) {
    m.min = arr[low];
    m.max = arr[low];
  } else if(n == 2) {
    m.min = min(arr[low], arr[low+1]);
    m.max = max(arr[low], arr[low+1]);
  } else {
    int mid = low + n / 2;
    MinMax m1 = findMinMax(arr, low, mid);
    MinMax m2 = findMinMax(arr, mid + 1, high);
    m.min = min(m1.min, m2.min);
    m.max = max(m1.max, m2.max);
  }
  return m;
}
```

Time Complexity: $O(n)$
Space Complexity: $O(1)$
Number of comparisons: $