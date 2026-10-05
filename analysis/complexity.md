# Complexity Analysis

## 1. Tree Height

Height is the number of edges on the longest root-to-leaf path.

The path:

CEO -> IT -> Development -> Frontend

contains 3 edges. Therefore, the tree height is **3 edges**, or **4 levels**.

The `tree_height()` function calculates the height recursively. A leaf node has height zero.

---

## 2. Complexity Analysis

Let:

- N = number of hierarchy nodes
- D = number of departments
- h = tree height
- w = maximum level width

For this hierarchy:

- N = 8
- D = 7
- h = 3
- w = 3

| Operation | Time Complexity | Additional Space |
|---|---|---|
| Construct hierarchy | O(N) | O(N) for stored tree |
| Level-order traversal | O(N) | O(N) allocated queue and depth arrays |
| Calculate height | O(N) | O(h + 1) recursive stack |
| Extract and sort department index | O(N + D²) worst case | O(N + D) traversal and index storage |
| Linear Search - Best Case | O(1) | O(1) |
| Linear Search - Average/Worst Case | O(D) | O(1) |
| Binary Search - Best Case | O(1) | O(1) |
| Binary Search - Average/Worst Case | O(log D) | O(1) |

Insertion sort costs O(D²) on average and in the worst case, and O(D) when the array is already sorted. It is sufficient for seven department names.

The construction function explicitly builds this fixed eight-node example. O(N) describes extending the same approach to an arbitrary-sized hierarchy.

Every traversal visits each node once. Height calculation examines every child subtree.

For this implementation, the allocated queue and depth arrays use O(N) space.

All fixed capacities must be increased if the hierarchy grows, or replaced with dynamic storage.

---

## 3. Search Comparison Details

For successful Linear Search with equally likely targets, the average number of comparisons is:

(D + 1) / 2 = 4

For an unsuccessful Linear Search, all D = 7 entries are checked.

For Binary Search, at most:

floor(log2 D) + 1 = 3

entries are examined for this non-empty list.

An empty list requires zero comparisons.

Names are strings. If the maximum name length is L, string comparison can cost O(L).

Therefore, more precise worst-case search bounds are:

- Linear Search: O(DL)
- Binary Search: O(L log D)

The usual DSA bounds above treat name comparison as constant time.

---

## 4. Traversal Behaviour

Breadth-first traversal visits all nodes at one depth before moving to the next.

The level-order sequence is:

CEO, HR, Finance, IT, Development, Testing, Frontend, Backend

This supports reports by level, while the stored parent-child links preserve reporting relationships.
