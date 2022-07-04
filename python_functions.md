# Python

## math

```
# infinity
float('inf')
float('-inf')
```

## sort
```
sorted(x, reverse = True)
```

```
# sort with key
def func(x):
    return x % 7

lst = [15, 3, 11, 7]
sorted(lst, key = func)

# use lambda function
tuples = [
     ('john', 'A', 15),
     ('jane', 'B', 12),
     ('dave', 'B', 10),
]
sorted(tuples, key=lambda x: x[2])   
```

## dictionary

```
d = {}

# iterate over keys
for key in d:

# iterate over keys and values
for key, value in d.items():

```

## set

```
s = set()
s.add(e)
s.remove(e)
```

## string

```
# reverse string
s[::-1]
```

```
s.upper()
s.lower()

# find pattern, return starting position (index)
s.find(pattern)
s.find(pattern, start_position)

s.startwith(pattern) # return false or true

# replacement
s.replace(old word, new word)

# remove spaces
s.lstrip()
s.rstrip()
# remove both beginning and ending whitespace
s.strip()
```

## collections

```
import collections

# dictionary of list
dic = collections.defaultdict(list)

# counter
counts = collections.Counter()
```

## exceptions

```
try:
    print "Hello World"

except IOError:
    print('An error occured trying to read the file.')

except ValueError:
    print('Non-numeric data found in the file.')

except ImportError:
    print "NO module found"

except EOFError:
    print('Why did you do an EOF on me?')

except KeyboardInterrupt:
    print('You cancelled the operation.')

except:
    print('An error occured.')
```

```
# raise exception
x = -1
if x < 0:
  raise Exception("Sorry, no numbers below zero")
```

## convert character to integer

```
# given a string, return integer representing the unicode character
ord('a') = 97
char(97) = 'a'
```

## convert integer to binary string

```
# convert integer number to a binary string prefixed with “0b”

bin(3) = '0b11'
```

## check type

```
isinstance(x, class)
```

## covert binary string to integer

```
int(x, base=10)
```

## iterate over element and index
```
for i, e in enumerate(lst):
```

## random
```
import random

number = random.random()
integer = random.randint(1,30)
randomlist = random.sample(range(10, 30), 5)
```

## data structure

### stack
```
stk = []
stk.append(ele)
last_ele = stk.pop()
size = len(stk)
```

### queue
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

### Linked list
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

### Tree
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

####  Binary search tree
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

### Trie

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
### heap

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

## read/ write files
### read text file
```
txt_file = open('data.txt', 'r')
lines = txt_file.readlines()

for line in lines:
    print(line)
```

### read/write json file
```
import json
with open('data.json') as f:
    data = json.load(f)

# load string to dict
json.loads(data)

with open('data.json', 'w') as f:
    json.dump(data, f)
```

### pickle
```
import pickle

with open('mylist.pkl', 'wb') as f:
	pickle.dump(mylist, f)

with open('mylist.pkl', 'rb') as f:
	mylist = pickle.load(f)
```

### write to csv file
```
import csv  

# field names  
fields = ['Branch', 'Year', 'CGPA']  

# data rows of csv file  
rows = [ ['COE', '2', '9.0'],  
         ['COE', '2', '9.1'],  
         ['IT', '2', '9.3']]  

# name of csv file  
filename = "records.csv"

# writing to csv file  
with open(filename, 'w') as csvfile:  
    # creating a csv writer object  
    csvwriter = csv.writer(csvfile)  

    # writing the fields  
    csvwriter.writerow(fields)  

    # writing the data rows  
    csvwriter.writerows(rows)
```

## file and directoy operations
### get all files matching suffix
```
import fnmatch
import os

# list sub directories
for root, subdirs, files in os.walk(rootdir):
    if len(subdirs) != 0:
        print(subdirs)
        
file_list = []
for root, dirnames, filenames in os.walk(rootdir):
    for filename in fnmatch.filter(filenames, '*.csv'):
        file_list.append(os.path.join(root, filename))

```
### check if directory exists
```
import os
is_exist = os.path.isdir(path)
if not is_exist:
    os.mkdir(f'./{path}')
```
### join directory and file path
```
dirname = os.path.dirname(__file__)
filename = os.path.join(dirname, 'relative/path/to/file/you/want')
```
### use enviroment variables
```
os.path.expandvars('$ENV/test')
```

### remove directory
```
import shutil

path = 'file_path'
shutil.rmtree(path)
```

## time operations
### datetime
```
from datetime import datetime, timedelta

datetime.strptime(time_str, '%Y-%m-%d %H:%M:%S')
(datetime.strptime(time_str, '%Y-%m-%d') + timedelta(days = 7)).strftime('%Y-%m-%d')

time_delta.total_seconds()/3600

epoch_time = 1571005498
datetime_time = datetime.fromtimestamp(epoch_time)
```
### timing code
```
import time
start_time = time.time()
main()
print("--- %s seconds ---" % (time.time() - start_time))

start = time.perf_counter()
main()
print(time.perf_counter() - start)
```
