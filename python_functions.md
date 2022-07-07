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

## regular expression
```
import re

number_or_symbol = re.compile('(\d+|[^ 0-9])')
print(re.findall(number_or_symbol, '1 +2-(4+ 6)'))
```