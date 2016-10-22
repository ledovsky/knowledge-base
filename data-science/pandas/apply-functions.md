# Применение функций к датасету


## Функции

* `.map` применяет функцию к Series и возвращает Series такого же размера
* `.apply` применяет функцию к DataFrame к столбцам или строкам
* `.applymap` применяет функцию к DataFrame поэлементно и возвращает DataFrame такого же размера

```python
df.apply(numpy.sqrt) # returns DataFrame
df.apply(numpy.sum, axis=0) # equiv to df.sum(0)
df.apply(numpy.sum, axis=1) # equiv to df.sum(1)

df = df.applymap(lambda x: '%.2f' % x)

def f(row):
    print row['column A']

df.apply(f, axis=1)
```


```python
grouped = df.groupby('column A')

print grouped.groups

for name, group in grouped:
    print name
    print group

print grouped.get_group('bar')

print grouped.sum()

grouped_C = grouped['C']

grouped.aggregate(np.sum)

```
