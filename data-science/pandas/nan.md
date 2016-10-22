# Работа с NaN

## Удаление NaN

```python
np.isnan(x)                         # Проврить, является ли число nan
df = df[pd.notnull(df['col1'])]     # Удалить строки, где в col1 nan
df.dropna()                         # Удалить строку, если в ней есть nan
df.dropna(subset=['col1', 'col2'])  # Удалить, если nan в col1 или col2
df.dropna(how='all')                # Удалить, только если вся строка nan
df.dropna(subset=['col1', 'col2'], how='all')
```

## Заполнение NaN

```python
df.fillna(0)
df.fillna(df.mean())
df.fillna(df.mean()['B':'C'])
```

[Ссылка на документацию](http://pandas.pydata.org/pandas-docs/stable/missing_data.html)
