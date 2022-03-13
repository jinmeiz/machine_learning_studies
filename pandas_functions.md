# Jupyter notebook/Pandas functions

## Progress bar
```
from tqdm import trange
    
for i in trange(len(num)):
```

```
from tqdm.auto import tqdm

# create and register a new `tqdm` instance with `pandas`
tqdm.pandas()

data['col_2'] = data['col_1'].progress_apply(lambda_function)
```

## Avoid warning
```
import warnings

warnings.filterwarnings('ignore')
```

## Functions
### change column type
```
df['col'].astype(str)
```
### convert string list from csv to list
```
from ast import literal_eval

data_pd['col'] = data_pd['col'].apply(literal_eval)
``` 
### group and aggregate
```
(df
 .groupby('col', as_index=False)
 .agg('sum')
 )
 
(df
 .groupby('col', as_index=False)['col']
 .agg({'col_count':'count'})
 .sort_values(by='col_count', ascending=False)
 )
```
### sort by value
```
df.sort_values(by=['col'], ascending=False)
```
### drop duplicates
```
df.drop_duplicates(subset=['col_1'])
```
### drop columns
```
df.drop(['B', 'C'], axis=1)
```
### apply function on a row
```
df.apply(fun, axis=1)

# apply function with argument
df[col].apply(fun, args=(arg1,))
```
### select the ith row
```
df.iloc[0]
```
### iterate rows
```
for index, row in df.iterrows():
    print(row['c1'], row['c2'])
```
### reset index
```
df = df.reset_index(drop=True)
```
### rename columns
```
df = df.rename(columns={'col_old': 'col_new', })

df.columns = cols
```

## Show all columns
```
import pandas as pd

pd.set_option('display.max_colwidth', -1)
```

## Read file
```
# without creating extra index column
pd.read_csv('data.csv', index_col=0)

# skip rows when reading csv
data = pd.read_csv(fname, skiprows=n)
```     

## Create dataframe from lists of list
```
# initialize list of lists  
data = [['DS', 'Linked_list', 10], ['DS', 'Stack', 9], 
        ['Algo', 'Greedy', 8], ['Algo', 'DP', 6], ]  
  
# Create the pandas DataFrame  
df = pd.DataFrame(data, columns = ['Category', 'Name', 'Marks']) 

Output:
Category         Name  Marks
0       DS  Linked_list     10
1       DS        Stack      9
3     Algo       Greedy      8
4     Algo           DP      6
```

## useful functions
```
# create dictionary with pandas columns
col_dict = dict(zip(df.col1, df.col2))

# lambda function
lambda x: col_dict[x]

# convert column to numpy array
np.array(df.col.values.tolist())
```

## Two dataframes
### append other dataframe
```
df1.append(df2, ignore_index=True)
```
### anti join:
```
df1[~df1[['label1','label2']].apply(tuple,1).isin(df2[['label1','label2']].apply(tuple,1))]
```

## Save and read file
### pandas dataframe to csv
```
import pandas as pd

 data_pd.to_csv('data.csv', index=False)
 pd.read_csv('data.csv', index_col=0)
```
### pickle
```
import pickle

with open('data.pkl', 'wb') as f:
    pickle.dump(data, f)
    
with open('data.pkl', 'rb') as f:
    data = pickle.load(f)
```

## Remove file
```
import os
 
if os.path.exists(file_name):
       os.remove(file_name)
``` 

## Indent codes
Tab
Shift + Tab

## Comment codes
Command + /
