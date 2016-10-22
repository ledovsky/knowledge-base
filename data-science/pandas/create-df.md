# Pandas - Создание DataFrames

## Создание DataFrames

```python
d = {'col1': ts1, 'col2': ts2}
df = pd.DataFrame(data=d, index=index)
df2 = pd.DataFrame(np.random.randn(10, 5)) 

headers = ['var1', 'var2']
rows = [[1, 2], [1, 3]]
df3 = pd.DataFrame(rows, columns=headers)

dict_list = [d1, d2]
df4 = pd.DataFrame(dict_list)

```

