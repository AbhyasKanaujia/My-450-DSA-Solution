# Heap

Source: [2.6.3 Heap - Heap Sort - Heapify - Priority Queues - Abdul Bari](https://youtu.be/HqPJF2L5h9U)

Heap is a special type of complete and full binary tree in which every node is greater than or equal to its children.

- The root of the tree is the maximum element in the tree.
- Duplicates are allowed.

```plaintext
              50
           /      \

    30                20
   /   \             /   \
15       10        8       16
```

`array: [50, 30, 20, 15, 10, 8, 16]`

- Insertion takes $O(log n)$ in worst case and $O(1)$ in best case.
- Deleting takes $O(log n)$ in worst case and $O(1)$ in best case.
- Heap sort is when you keep deleting the root node and inserting it at the end. The end result is a sorted array.

## Heap Sort

1. Create a max heap from the array.
2. Delete the root node and insert it at the end.
3. Repeat step 2 until the heap is empty.

## Heapify

Source: [L-3.11: Build Heap in O(n) time complexity | Heapify Method | Full Derivation with example by **Gate Smasher**
](https://www.youtube.com/watch?v=8noP3YjjJCM)

Time Complexity: <!-- $O(n)$ --> <img style="transform: translateY(0.1em); filter: invert();" src="https://render.githubusercontent.com/render/math?math=O(n)">

- Leaf nodes are not compared with their children. The number of leaf nodes is $\frac{n}{2}$. Thus we get to ignore $\frac{n}{2}$ comparisons which makes the algorithm fast.
- 

## Priority Queues

Priority queues is a data structure that allows you to insert elements in a certain order. This is implemented using a heap.

### Priority Queue in C++

Source: [std::priority_queue in C++](https://www.youtube.com/watch?v=JSqznrzWGvc)

- Gives largest/smallest element in $O(1)$ time.
- By default vector is used as the underlying data structure.
- Insertion and deletion takes $O(log n)$ time.
- Functions available are:
  - `push` to insert an element.
  - `pop` to delete the element.
  - `top` to get the top element.
  - `empty` to check if the queue is empty.
  - `size` to get the size of the queue.

#### Example

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
   priority_queue<int> pq;

   for(int x: {1,8,2,5,3,6,4,7})
      pq.push(x);

   while(!pq.empty()) {
      cout << pq.top() << " ";
      pq.pop();
   }

   return 0;
}
```
