# Pandas - Удаление дубликатов и констант


## Удалить дубликаты в столбцах

```python
def delete_duplicated_features(X):
    '''
    Check for duplicated columns and delete them
    '''
    
    from itertools import combinations
    
    features_before = X.shape[1]
    feat_names_delete = []

    # Iterating through all pair combinations of columns
    for feat1, feat2 in combinations(X.columns, 2):
        if np.array_equal(X[feat1], X[feat2]):
            feat_names_delete.append(feat2)

    feat_names_delete = np.unique(feat_names_delete)
    
    features_deleted = len(feat_names_delete)
    X = X.drop(labels=feat_names_delete, axis=1)
    
    print 'Deleting duplicated features {}/{}'.format(features_deleted, features_before)
    
    return X
```

## Удалить столбцы константы

```python
def delete_constant_features(X):
    """
    Check if feature's variance is equal to zero
    If so, deletes a feature
    """
    
    features_before = X.shape[1]
    feat_names_delete = []
    
    for feat in X.columns:
        if X[feat].std() == 0:
            feat_names_delete.append(feat)
    
    features_deleted = len(feat_names_delete)
    
    X = X.drop(labels=feat_names_delete, axis=1)
    
    print 'Deleting constant features {}/{}'.format(features_deleted, features_before)
    
    return X
```

## Удалить дубликаты в строках

```python
# Для всей таблицы
df.duplicated()               
df.drop_duplicates()
# Для столбца
df.duplicated('col1')
df.drop_duplicates('col1')
```

