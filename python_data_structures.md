# Python data structures

## stack
```
stk = []
stk.append(ele)
last_ele = stk.pop()
size = len(stk)
```

## queue
```
from collections import deque

q = deque()
q.append(4)
q.append(5)
q.appendleft(6)  # [6, 4, 5]

q.popleft()      # 6
q.pop()          # 5

size = len(q)
```

## Linked list
```
class Node:
    def __init(self, key, val):
        self.key = key
        self.val = val
        self.prev = None
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = Node(None, 'head')
        self.tail = Node(None, 'tail')
        self.head.next = self.tail
        self.tail.prev = self.head

    def get_head(self):
        return self.head.next

    # bumping node to the back of the list
    def add(self, node):
        prev = self.tail.prev
        prev.next = node
        node.prev = prev
        node.next = self.tail
        self.tail.prev = node

    def remove(self, node):
        prev = node.prev
        next = node.next
        prev.next = nxt
        nxt.prev = prev

```

## Tree
in-order: traverse left node, current node, then right
```
d b e  a  f c g
-------------
left  |r| right
```
pre-order: traverse current node, left, then right
```
a  b d e  c f g
-------------
r | left | right
```
post-order, traverse left node, then right, then current
```
class Node:
    def __init__(self, data, left=None, right=None):
        self.data = data
        self.left = left
        self.right = right
```

###  Binary search tree
```
class BST:
    def __init__(self):
        self.root = None

    def insert(self, x):
        if not self.root:
            self.root = Node(x)
        else:
            self._insert(x, self.root)

    def _insert(self, x, root):
        if x < root.data:
            if not root.left:
                root.left = Node(x)
            else:
                self.insert(x, root.left)

        else:
            if not root.right:
                root.right = Node(x)
            else:
                root.insert(x, root.right)

# another implementation
def insert(root, key):
    if root is None:
        return Node(key)
    else:
        if root.val == key:
            return root
        elif root.val < key:
            root.right = insert(root.right, key)
        else:
            root.left = insert(root.left, key)
    return root

```

## Trie

A trie is a kind of tree whose nodes typically represent strings, where every descendant of a node shares a common prefix. The simplest way to implement a trie is to use a nested dictionary, where each key maps to a dictionary whose keys are successive letters in a given word.

```python
'd':
	{'o':
		{'g': {'#': True}}
	}
```



```python
ENDS_HERE = '#'

class Trie:
  def __init__(self):
    self.trie = {}

  def insert(self, text):
    trie = self.trie
    for char in text:
      if char not in trie:
        trie[char] = {}
      # traverse trie
      trie = trie[char]
    # mark the end of string
    trie[ENDS_HERE] = True

  def find(self, prefix):
    trie = self.trie
    for char in prefix:
      if char in trie:
        trie = trie[char]
      else:
        return None

    return trie

```
## heap

```
import heapq

heapq.heapify(lst)         # O(NlogN)
heapq.heappush(lst, ele)   # O(logN)
heapq.heappop(lst)         # O(logN)

# time complexity?
heapq.nlargest(n, lst)
heapq.nsmallest(n, lst)
```


## bisect

```
from bisect import bisect
```

https://www.geeksforgeeks.org/bisect-algorithm-functions-in-python/

1. bisect(list, num, beg, end) :- This function returns the position in the sorted list, where the number passed in argument can be placed so as to maintain the resultant list in sorted order. If the element is already present in the list, the right most position where element has to be inserted is returned. This function takes 4 arguments, list which has to be worked with, number to insert, starting position in list to consider, ending position which has to be considered.

2. bisect_left(list, num, beg, end) :- This function returns the position in the sorted list, where the number passed in argument can be placed so as to maintain the resultant list in sorted order. If the element is already present in the list, the left most position where element has to be inserted is returned.

3. bisect_right(list, num, beg, end) :- This function works similar to the “bisect()” and mentioned above.

4. insort(list, num, beg, end) :- This function returns the sorted list after inserting number in appropriate position, if the element is already present in the list, the element is inserted at the rightmost possible position.

5. insort_left(list, num, beg, end) :- This function returns the sorted list after inserting number in appropriate position, if the element is already present in the list, the element is inserted at the leftmost possible position.

6. insort_right(list, num, beg, end) :- This function works similar to the “insort()” as mentioned above.
