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

## Indent codes
Tab
Shift + Tab

## Comment codes
Command + /