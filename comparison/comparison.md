# Comparison Table

## 1. Observed Search Results

These counts come from executing the C program on the supplied hierarchy.

Both searches use the same sorted department array. Preprocessing is excluded from per-query counts. These are logical entry comparisons, not elapsed times.

| Query | Result | Linear Search | Binary Search | Fewer Comparisons |
|---|---|---:|---:|---|
| Backend | Found at index 0 | 1 | 3 | Linear |
| HR | Found at index 4 | 5 | 3 | Binary |
| Testing | Found at index 6 | 7 | 3 | Binary |
| Marketing | Not found | 7 | 3 | Binary |
| Total | Four queries | 20 | 12 | Binary |

Binary Search used **8 fewer comparisons (40% fewer)** for these four queries after sorting.

This does not establish a 40% runtime improvement or include sorting cost.

---

## 2. Comparison of Approaches

| Criterion | General Tree | Array with Linear Search | Sorted Array with Binary Search |
|---|---|---|---|
| Reporting relationships | Directly stores parent-child links | Names alone lose links | Names alone lose links |
| Level-based reporting | O(N) breadth-first traversal | Not available from names alone | Not available from names alone |
| Lookup worst case | O(N) traversal | O(D) | O(log D) |
| Ordering prerequisite | None | None | Must be sorted |
| Search auxiliary space | O(N) for this BFS implementation | O(1) | O(1), iterative |
| Preprocessing here | O(N) construction | O(N) extraction; sorting unnecessary | O(N + D²) extraction and insertion sort |
| Updates | Update parent-child links within capacity | Append if capacity permits | Insertions may shift O(D) entries |
| Best use | Organisational reporting | Small lists or occasional searches | Repeated searches in mostly static data |

N = number of hierarchy nodes.

D = number of departments.

Name comparisons are treated as constant time in this table.

Section 1 provides string-length costs, height calculation and allocated space details.
