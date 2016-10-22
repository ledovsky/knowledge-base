# String formatting - форматирование строк
Date: 2016-03-01

Форматирование строк - полезный инструмент, который позволяет создать строку с использованием переменных. Состоит из шаблона и списка переменных. В шаблоне есть предопределенный текст и места для вставки переменных с указанными параметрами.

Используется в основном для вывода результатов работы программы/метода.

## Примеры

    :::python
    >>> '{0:.2f} {1:.2f}'.format(float(45)/89,float(34)/89)
    '0.51 0.38'
    
    >>> "int: {0:d};  hex: {0:#x};  oct: {0:#o};  bin: {0:#b}".format(42)
    'int: 42;  hex: 0x2a;  oct: 0o52;  bin: 0b101010'
    
    >>> '{0}, {1}, {0}, {2}'.format('a', 'b', 'c')
    'a, b, a, c'
    
    >>> 'Coordinates: {latitude}, {longitude}'.format(latitude='37.24N', longitude='-115.81W')
    'Coordinates: 37.24N, -115.81W'
    
    >>> "Whatever: {items[0]}".format(items = [1, 2, 3])
    'Whatever: 1'

## Основные типы данных

    :::python
    f - fixed point
    d - decimal integer
    e - exponent notation
    s - string
    % - percentage

## Полный синтаксис метода

[Ссылка на документацию](https://docs.python.org/2/library/string.html#format-string-syntax)

    :::python
    replacement_field ::=  "{" [field_name] ["!" conversion] [":" format_spec] "}"
    field_name        ::=  arg_name ("." attribute_name | "[" element_index "]")*
    arg_name          ::=  [identifier | integer]
    attribute_name    ::=  identifier
    element_index     ::=  integer | index_string
    index_string      ::=  <any source character except "]"> +
    conversion        ::=  "r" | "s"
    
    format_spec ::=  [[fill]align][sign][#][0][width][,][.precision][type]
    fill        ::=  <any character>
    align       ::=  "<" | ">" | "=" | "^"
    sign        ::=  "+" | "-" | " "
    width       ::=  integer
    precision   ::=  integer
    type        ::=  "b" | "c" | "d" | "e" | "E" | "f" | "F" | "g" | "G" | "n" | "o" | "s" | "x" | "X" | "%"



