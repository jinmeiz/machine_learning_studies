# Pyspark functions

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
