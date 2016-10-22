# Словари в python

## Создание, добавление, выбор, удаление

```python
# Создание
d = {'key1': value1, 'key2': value2}
d = dict([('key1', value1), ('key2', value2)])

# Добавление
d['key3'] = value3

# Выбор элементов
d['key1']           # Возвращает значение по ключу, либо ошибку
d.get('key1')       # Если ключа нет, отвечает None, а не ошибку
d.keys()            # Возвращает ключи списком

# Удаление элементов
d.pop('key1')       # value1
```

## Циклы

```python
# Python 2
for key, value in d.iteritems():
    print key
    print value

# Python 3
for key, value in d.items():
    print(key)
    print(value)
```

## обработка несозданных ключей и defaultdict

Примеры, когда встречается задача

* Когда приходит неизвестное количество параметров в
    словарях и необходимо задать значение по умолчанию. 
* Когда динамически создается словарь

Варианты

```python
# Проверка
if k in d.keys():
    res = d[k]

# Метод setdefault
res = d.setdefault(k, value_if_not_exists)

# defaultdict
from collection import defaultdict
default_factory = some_function
d = defaultdict(default_factory)
```

## OrderedDict

```python
from collections import OrderedDict

```
