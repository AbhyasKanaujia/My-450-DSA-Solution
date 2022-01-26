# STL

## Containers

### Set

#### Use case

- count unique elements
- ascending order is important

#### Properties

- Only Stores unique elements
- No indexing
- Elements are stored in sorted order
- No duplicate elements
- Immutable values

#### Basic Functions

1. `set.insert(x)`
2. `set.erase(x)`
3. `set.find(x)`
4. `set.count(x)`
5. `set.empty()`
6. `set.size()`
7. `set.clear()`
8. `set.begin()`
9. `set.end()`

#### Alternative: unordered_set

Faster than set. Use when you don't care about the order of elements.

##### Unique use case

- order is not important only presence is important

##### Uniqueness

- Order of elements is not guaranteed

#### Computational Complexity

##### Set's time complexity

<!-- $O(\log N)$ --> <img style="transform: translateY(0.1em); filter: invert();" src="https://render.githubusercontent.com/render/math?math=O(%5Clog%20N)">

##### unordered_set's time complexity

<!-- $O(1)$ --> <img style="transform: translateY(0.1em); filter: invert();" src="https://render.githubusercontent.com/render/math?math=O(1)">

