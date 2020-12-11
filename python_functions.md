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
s.add(v)
```

## stack
```
stk = []
stk.append(ele)
last_ele = stk.pop()
size = len(stk)
```

## queue
```
q = collections.deque()
q.append(ele)
first_ele = q.popleft()
size = len(q)
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

## heap 

```
import heapq

heapq.heapify(lst)
heapq.heappush(lst, ele) 
heapq.heappop(lst)

# time complexity?
heapq.nlargest(n, lst)
heapq.nsmallest(n, lst)
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

## read text file
```
txt_file = open('data.txt', 'r') 
lines = txt_file.readlines() 

for line in lines: 
    print(line)
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
