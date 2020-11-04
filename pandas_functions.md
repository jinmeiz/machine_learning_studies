# Jupyter notebook/Pandas functions

## Progress bar

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
### group and aggregate
```
(df
 .groupby('col', as_index=False)
 .agg('sum')
 )
```
### sort by value
```
df.sort_values(by=['col'], ascending=False)
```

## Show all columns
```
import pandas as pd

pd.set_option('display.max_colwidth', -1)
```

## Read file without creating extra index column
```
import pandas as pd

pd.read_csv('data.csv', index_col=0)
```

## Read list of strings from csv
```
from ast import literal_eval

data_pd['col'] = data_pd['col'].apply(literal_eval)
```

## Drop duplicates
```
df.drop_duplicates(subset=['col_1'])
```

## Remove file
```
import os
 
if os.path.exists(file_name):
       os.remove(file_name)
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

## useful functions
```
# drop column
df.drop(['col'], axis = 1)

# create dictionary with pandas columns
col_dict = dict(zip(df.col1, df.col2))

# lambda function
lambda x: col_dict[x]

# convert column to numpy array
np.array(df.col.values.tolist())
```

## sort
```
df.sort_values(by='col1', ascending=False)
```

## append other dataframe
```
df1.append(df2, ignore_index=True)
```

## groupby
```
(df
 .groupby('col', as_index=False)['col']
 .agg({'col_count':'count'})
 .sort_values(by='col_count', ascending=False)
 )
```

## Indent codes
Tab
Shift + Tab

## Comment codes
Command + /
