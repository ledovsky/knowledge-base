# Базовый синтаксис
Date: 2016-02-20

## Операторы - особенности

    5 / 2            # целочисленное деление (python 2)
    5 / float(2)     # деление float
    from __future__ import division     # float деление по умолчанию
    
    number % 2 == 0  # остаток от деления
    x**2             # возведение в степень

## Циклы
  
    :::python
    # Чаще всего используется итерирование по объектам
    lst = ['a', 'b', 'c']
    for item in lst:
        print item
    
    # Но можно итерировать и по счетчику
    for x in range(10):
        print x
    
    i = 0
    while i < 10:
        i += 1
        print i


## Функция и класс

    :::python
    def foo(arg1, arg2):
        return arg1 + arg2
    
    class Bar(object):
        u'''При описании класса в скобках - от чего наследуем
        По умолчанию класс нужно наследовать от object. Это дает доступ к ряду стандартных инструментов для работы с ним.
        
        Каждая функция в классе содержит self в начале
        self позволяет обращаться к объекту 
        
        Этот текст называется docstring, описание класса или функции      
        '''
    
        # конструктор
        def __init__(self, arg1, arg2):
            self.arg1 = arg1
            self.arg2 = arg2
        
        def get_sum(self):
            return (self.arg1 + self.arg2)
    
    bar = Bar(2, 3)
    print bar.get_sum()
    # возвращает 5
    
    print bar.__doc__
    # возвращает docstring

## If Statement

    :::python
    # Statement
    if condition: statement
    if condition:
        block
    else:
        block
    
    # Expression
    expression_if_true if condition else expression_if_false

## Списки

### Создание, генераторные выражения, выбор элементов

Обычное создание списка

    :::python
    l = [1, 2, 3]
    l = list(1, 2, 3)

Создание с помощью генераторного выражения (list comprehension) с использованием итерируемого объекта (см. [Продвинутый синтаксис]({filename}advanced.md)).
    
    :::python
    l = [i*2 for i in xrange(5)]
    print l
    # [0, 2, 4, 6, 8]

Выбор элементов и подсписков. Нумерация элементов начинается с 0.

    :::python
    l[1]                # 1-й элемент
    l[-1]               # Последний элемент
    l[1:3]              # C 1-го по 2-й
    l[3:]               # C 3-го до конца
    l[::2]              # Каждый второй, начиная с 0-го

### Добавление и удаление элементов, длинна

    :::python
    # Добавление элементов
    
    l = [1, 2, 3]
    l.append([4,5])
    print l             # [1, 2, 3, [4, 5]]
    
    l = [1, 2, 3]
    l.extend([4,5])
    print l             # [1, 2, 3, 4, 5]
    
    l = [1, 2, 3]
    l = l + [4, 5]
    print l             # [1, 2, 3, 4, 5]
                        # тот же .extend()
    
    # Удаление элементов
    l = [1, 2, 3, 4, 5]
    print l.pop()       # 5 
    print l             # [1, 2, 3, 4]
    l.pop(2)            # 3
    print l             # [1, 2, 4]
    
    # Длина
    len(l)

### Циклы, enumerate

    :::python
    for item in lst:
        print item
    
    for index, item in enumerate(lst):
        print index
        print item

## Кортежи (tuples)

Неизменяемы, не поддерживают изменение и удаление элементов, только чтение. Работают гораздо быстрее списков. Много используются в невидимой части Python. В коде встречаются обычно при передаче параметров функциям.

    :::python
    t = (1, 2, 3)
    t[0] # 1




