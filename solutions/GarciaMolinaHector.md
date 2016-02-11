# Hector Garcia-Molina Solutions
<!-- TOC depthFrom:2 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Hector Garcia-Molina Solutions](#hector-garcia-molina-solutions)
  - [EE Quals Question 2007](#ee-quals-question-2007)
    - [Part A](#part-a)
    - [Part B](#part-b)

  - [Binary Search](#binary-search)
    - [Original Question](#original-question)
    - [Extra Credit](#extra-credit)

<!-- /TOC -->

## EE Quals Question 2007
### Part A
The buffer manager can use any of the [cache replacement strategies](https://en.wikipedia.org/wiki/Cache_algorithms) that are commonly used today. Each has its unique tradeoffs. Some of the common ones are:
- Least Recently Used (LRU)
  - Discards the least recently used items first. This requires keeping track of what was used when, which can be expensive. Generally require using "age bits" for cache-lines. Each time a cache-line is used, the age of all other cache-lines changes.

- Most Recently Used
  - It was foundtha wen a file is being repeatedly scanned in a looping sequential reference pattern, MRU is the best replacement algorithm. This is also useful for random access patterns or repeated scans over large datasets.
  - Useful in situations where the older an item is, the more likely it is to be accessed.

- Random Replacement
  - Randomly selects a candidate item and discards it. Because of it's simplicity it is lightweight to implement and is used in ARM processors.

- Direct Mapped
  - Used for the highest-speed CPU caches because of it's simplicity to implement
  - The address of the new item is used to calculate the single location in the cache where it is allowed to go.

- X-way Set Associative:
  - Similar to direct mapped, but now the address of the new item maps to one of X possible locations in the cache.
  - Can use LRU or least frequently used etc.

### Part B

```c
block* NEW; // points to the record that represents the most recently accessed buffer
block* OLD; // points to the record that represents the least recently accessed buffer
REGISTER(P) {
  // He is essentially asking us to write code that moves P to the top of the linked list

  // Case buffer is empty
  if (!NEW && !OLD) {
    NEW = P;
    OLD = P;
    return;
  }

  // Case Moving from NEW
  if (NEW == P) {
    return;
  }

  // Case Moving from Tail
  if (OLD == P) {
    OLD->pev->next = NULL // cut off from tail
    NEW->prev = P;        // Add to head
    P->next = NEW;
    P->prev = NULL;        
    NEW = P               // Update NEW
    return;
  }

  // Case Middle of list
  P->prev->next = P->next;
  P->next->prev = P->prev;

  P->prev = NULL
  P->next = NEW
  NEW->prev = P;
  NEW = P
}
```

## Binary Search
### Original Question

```python
def binary_search_recursive(A, V, imin, imax):
  if (imax < imin):
    # Array is empty
    return (False, 0)
  else:
    # calculate midpoint
    imid = imin + ((imax - imin) / 2) # avoid overflow
    if (A[imid] > V):
      return binary_search(A, V, imin, imid - 1)
    elif (A[imid] < V):
      return binary_search(A, key, imid + 1, imax)
    else:
      return (True, imid)

def binary_search_iterative(A, V, imin, imax):
  while (imin <= imax):
    imid = imin + ((imax - imin) / 2) # avoid overflow
    if (A[imid] == V):
      return (True, imid)
    elif: (A[imid] < V):
      imin = imid + 1
    else:
      imax = imid - 1

  return (False, 0)

def FIND(V):
  return binary_search_recursive(A, V, 0, N-1)
```

### Extra Credit
To handle duplicates, we'd need to determine what the desired output is. For example, Can I just return any index? Or, do I need to return the first occurance? We would then updated our algorithm so that once a value was found, we march left until we reach a different value. Another idea is to continue to binary search left, remembering the last found location until it is no longer found.
