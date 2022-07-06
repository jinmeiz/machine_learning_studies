## plot dates as x axis
```
import matplotlib.pyplot as plt

plt.figure(figsize=(10, 6))

df['dates'] = pd.to_datetime(df['date_str'])
plt.plot(df.dates, df[cols])

plt.ylabel('y')
plt.title('chart example')

plt.legend(cols, loc='best')
plt.show()
```

## plot horizontal line
```
plt.axhline(0, color="grey", linewidth=1)
```

## plot bar chart
```
plt.bar(num_bars, list_1, width, label='label_1')
plt.bar(num_bars+width, list_2, width, label='label_2')

plt.xticks(num_bars, list_xtick_str)
```

## scatter plot
```
plt.scatter(data1, data2)
```
