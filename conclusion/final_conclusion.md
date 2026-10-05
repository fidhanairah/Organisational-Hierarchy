# Final Conclusion

Use a general tree for organisational reporting and a sorted department array with Binary Search for repeated lookup.

The tree preserves reporting links and displays four levels. Its height is three edges.

Binary Search made 12 comparisons across the four queries, versus 20 for Linear Search. Its O(log D) worst-case lookup scales better than O(D).

Linear Search remains reasonable for seven names and occasional queries. It wins for Backend and needs no sorting.

Binary Search benefits repeated searches after preprocessing.

The fixed tree suits this hierarchy, but growth requires larger capacities or dynamic storage. Updates must keep the search index consistent.

Multiple managers require a graph, while duplicate department names require IDs.
