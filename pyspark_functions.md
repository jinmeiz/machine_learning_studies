# Pyspark functions

## common imports
```
from pyspark.sql import Column
from pyspark.sql import functions as F
from pyspark.sql.window import Window
```

## create spark session from spark context
```
spark = SparkSession(spark_context)
```

## create spark dataframe from pandas dataframe
```
spark_df = spark.createDataFrame(pandas_pd)
```

## rename column
```
df.withColumnRenamed(existingName, newNam)
```

## get items from array column
```
df.withColumn('item_0', F.col('array_col').getItem(0))
```

## spark udf
```
from pyspark.sql.types import BooleanType, StringType, IntegerType

def func(x):
  	pass

udf = F.udf(func, returnType=StringType())

df.withColumn(new_col_name, udf(col_name)))
```

## aggregate to array with condition
```
F.collect_list(F.when(F.col('col_1') == False, F.col('col_2'))).alias('col_3')
```

## check if an array contains certain string
```
df.where(F.array_contains(F.col('col_name'), str_match))
```

## get substring
```
df.withColumn(new_col_name, F.substring(col_name, 1, 3))
```

## drop duplicates
```
df.dropDuplicates(['col_1', 'col_2'])
```

## drop column
```
df.drop('col')
```

## fill null
```
df.fillna('null', subset=[col_name])
```

## check array overlap
```
def contains_target() -> Column:
    return F.array_contains(F.collect_set(F.col("col_name")).over(Window.partitionBy("id")), TARGET)

def contains_targets() -> Column:
    return F.arrays_overlap(
        F.collect_set(F.col("col_name")).over(Window.partitionBy("id")),  F.array(*[F.lit(v) for v in TARGETS]),
    )
```
    
## row number
```
F.row_number().over(Window.partitionBy('col_1').orderBy('col_2'))
```

## rank by group
```
df.withColumn('rank',
              F.row_number().over(Window
                                  .partitionBy('partition_col')
                                  .orderBy(F.col('orderby_col'))
                                  )
              )
```

## covert string to date
```
# https://docs.oracle.com/javase/tutorial/i18n/format/simpleDateFormat.html

df
.withColumn('date', F.to_date(c.date_str, 'MM/dd/yyyy'))
.where(c.date > datetime.date(2020, 6, 1))
```

## sample
```
df.sample(fraction=0.01, seed=42)
```
