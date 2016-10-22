# Наброски для тренинга по python

## Осторожно, mutable объекты

```python
def add_empty_rows(df, n_rows, token=np.nan):
    n_col = len(df.columns)
    data = [[token for i in range(n_col)] for j in range(n_rows)]
    empty_df = pd.DataFrame(data, columns=df.columns)
    pd = pd.concat([empty_df, df, empty_df], axis=1)
    return pd

    # Правильно
    res = pd.concat([empty_df, df, empty_df], axis=1)
    return res
```
