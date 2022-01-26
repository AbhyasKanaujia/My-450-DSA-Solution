# HeaSource: [2.6.3 Heap - Heap Sort - Heapify - Priority Queues - Abdul Bari](https://youtu.be/HqPJF2L5h9U)

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

Time Complexity: $O(n)$

## Priority Queues

Priority queues are a data structure that can be used to implement a priority queue.