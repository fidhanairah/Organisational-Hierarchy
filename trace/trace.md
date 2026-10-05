# Trace Tables

## 1. Level-Order Traversal

The hierarchy is traversed using Breadth-First Search (BFS).

| Step | Visited | Depth | Head | Tail | Queue after enqueuing children |
|---:|---|---:|---:|---:|---|
| 1 | CEO | 0 | 1 | 4 | HR, Finance, IT |
| 2 | HR | 1 | 2 | 4 | Finance, IT |
| 3 | Finance | 1 | 3 | 4 | IT |
| 4 | IT | 1 | 4 | 6 | Development, Testing |
| 5 | Development | 2 | 5 | 8 | Testing, Frontend, Backend |
| 6 | Testing | 2 | 6 | 8 | Frontend, Backend |
| 7 | Frontend | 3 | 7 | 8 | Backend |
| 8 | Backend | 3 | 8 | 8 | Empty |

---

## 2. Insertion Sort

The department names are extracted from the hierarchy and sorted alphabetically using insertion sort.

| Pass | Inserted key | Array after pass |
|---:|---|---|
| 0 | Initial | HR, Finance, IT, Development, Testing, Frontend, Backend |
| 1 | Finance | Finance, HR, IT, Development, Testing, Frontend, Backend |
| 2 | IT | Finance, HR, IT, Development, Testing, Frontend, Backend |
| 3 | Development | Development, Finance, HR, IT, Testing, Frontend, Backend |
| 4 | Testing | Development, Finance, HR, IT, Testing, Frontend, Backend |
| 5 | Frontend | Development, Finance, Frontend, HR, IT, Testing, Backend |
| 6 | Backend | Backend, Development, Finance, Frontend, HR, IT, Testing |

---

# 3. Linear Search Trace

## Search: Backend

| Comparison | Index | Entry | Result |
|---:|---:|---|---|
| 1 | 0 | Backend | Found |

Total comparisons: **1**

---

## Search: HR

| Comparison | Index | Entry | Result |
|---:|---:|---|---|
| 1 | 0 | Backend | Continue |
| 2 | 1 | Development | Continue |
| 3 | 2 | Finance | Continue |
| 4 | 3 | Frontend | Continue |
| 5 | 4 | HR | Found |

Total comparisons: **5**

---

## Search: Testing

| Comparison | Index | Entry | Result |
|---:|---:|---|---|
| 1 | 0 | Backend | Continue |
| 2 | 1 | Development | Continue |
| 3 | 2 | Finance | Continue |
| 4 | 3 | Frontend | Continue |
| 5 | 4 | HR | Continue |
| 6 | 5 | IT | Continue |
| 7 | 6 | Testing | Found |

Total comparisons: **7**

---

## Search: Marketing

| Comparison | Index | Entry | Result |
|---:|---:|---|---|
| 1 | 0 | Backend | Continue |
| 2 | 1 | Development | Continue |
| 3 | 2 | Finance | Continue |
| 4 | 3 | Frontend | Continue |
| 5 | 4 | HR | Continue |
| 6 | 5 | IT | Continue |
| 7 | 6 | Testing | Continue |

All entries exhausted.

Total comparisons: **7**

---

# 4. Binary Search Trace

## Search: Backend

| Comparison | Low | High | Mid | Entry | Action |
|---:|---:|---:|---:|---|---|
| 1 | 0 | 6 | 3 | Frontend | high = mid - 1 |
| 2 | 0 | 2 | 1 | Development | high = mid - 1 |
| 3 | 0 | 0 | 0 | Backend | Found |

Total comparisons: **3**

---

## Search: HR

| Comparison | Low | High | Mid | Entry | Action |
|---:|---:|---:|---:|---|---|
| 1 | 0 | 6 | 3 | Frontend | low = mid + 1 |
| 2 | 4 | 6 | 5 | IT | high = mid - 1 |
| 3 | 4 | 4 | 4 | HR | Found |

Total comparisons: **3**

---

## Search: Testing

| Comparison | Low | High | Mid | Entry | Action |
|---:|---:|---:|---:|---|---|
| 1 | 0 | 6 | 3 | Frontend | low = mid + 1 |
| 2 | 4 | 6 | 5 | IT | low = mid + 1 |
| 3 | 6 | 6 | 6 | Testing | Found |

Total comparisons: **3**

---

## Search: Marketing

| Comparison | Low | High | Mid | Entry | Action |
|---:|---:|---:|---:|---|---|
| 1 | 0 | 6 | 3 | Frontend | low = mid + 1 |
| 2 | 4 | 6 | 5 | IT | low = mid + 1 |
| 3 | 6 | 6 | 6 | Testing | high = mid - 1 |

Search stops with:

```text
low = 6
high = 5

Marketing is not found.

Total comparisons: **3**
