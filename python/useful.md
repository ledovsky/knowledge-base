# Полезные функции
Date: 2016-03-01

    :::python
    type(x)                             # тип данных
    from __future__ import division     # float деление по умолчанию
    help('modules')                     # вывести модули

## Функция для упллощения списков

```python
def flatten(l):
    for el in l:
        if isinstance(el, collections.iterable) and not isinstance(el, basestring):
            for sub in flatten(el):
                yield sub
        else:
            yield el
```
