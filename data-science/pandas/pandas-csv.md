# Pandas - Работа с CSV

```python
pd.read_csv('path')             # Чтение csv
df.to_csv('path', index=False)  # Запись csv
```

Полезные параметры:

```python
sep=';'                     # Указать разделитель столбцов
decimal='.'                 # Указать разделитель дробной части
thousands=','               # Указать разделитель тысяч
header=None                 # Если нет заголовка
names=['col1', 'col2']      # Указать заголовок, header=None уже не нужно
na_values=['NA#', '###']    # Как распознать NaN, если не работает само
true_values='T'             # Аналогично
false_values='F'            # Аналогично
```

Добавить про работу с датами (когда будет практический кейс)

Как прочитать большой csv файл:

```python
tp = pd.read_csv('file.csv', iterator=True, chunksize=1000) 
df = pd.concat(tp, ignore_index=True)
```
