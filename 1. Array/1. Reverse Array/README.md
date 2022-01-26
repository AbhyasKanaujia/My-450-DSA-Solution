# Reverse The Array

> Write a program to reverse an array or string

[link](https://www.geeksforgeeks.org/write-a-program-to-reverse-an-array-or-string/)

Level: Basic

Source: GFG

## Two Pointer Approach

1. `p1 = 0`
2. `p2 = n-1`
3. Repeat while `p1 < p2`
   1. Swap value at `p1` and `p2`
   2. `p1++` and `p2--`

```cpp
string reverseWord(string str){
    int p1 = 0, p2 = str.size() - 1;
    while(p1 < p2)
        swap(str[p1++], str[p2--]);
    return str;
}
```

Time Complexity: <!-- $O(n)$ --> <img style="transform: translateY(0.1em); filter: invert();" src="https://render.githubusercontent.com/render/math?math=O(n)">

Space Complexity: <!-- $O(1)$ --> <img style="transform: translateY(0.1em); filter:invert();" src="https://render.githubusercontent.com/render/math?math=O(1)">

## Naive Approach

1. `rev = []`
2. `k = 0`
3. Traverse the array from `n - 1` to `0`
   1. `rev[k++] = arr[i]`
4. return `rev`

```cpp
string reverseWord(string str){
    string rev(str.size(), ' ');
    int k = 0;
    for(int i = str.size() - 1; i >= 0; i--)
        rev[k++] = str[i];
    return rev;
}
```

Time Complexity: <!-- $O(n)$ --> <img style="transform: translateY(0.1em); filter: invert();" src="https://render.githubusercontent.com/render/math?math=O(n)">

Space Complexity: <!-- $O(n)$ --> <img style="transform: translateY(0.1em); filter: invert();" src="https://render.githubusercontent.com/render/math?math=O(n)">

## Using STL

```cpp
string reverseWord(string str){
    reverse(str.begin(), str.end());
    return str;
}
```

Time Complexity: <!-- $O(n)$ --> <img style="transform: translateY(0.1em); filter: invert();" src="https://render.githubusercontent.com/render/math?math=O(n)">

Space Complexity: <!-- $O(1)$ --> <img style="transform: translateY(0.1em); filter: invert();" src="https://render.githubusercontent.com/render/math?math=O(1)">
