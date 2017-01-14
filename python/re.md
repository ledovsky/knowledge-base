# Регулярные выражения

## Основные функции

    # Поиск
    match = re.search(pattern, text)

    # Выделить полное совпадение
    match.group()

    # Выделить touple из групп
    match.groups()

    # Хорошая функция - ищет все совпадения
    # Возвращает список совпадений если групп нет
    # либо список touples из групп
    matches = re.findall(pattern, text)

    # Не использовать! Неэффективная функция
    match = re.match(pattern, text)
    # То же, что и search, только работает будто
    match = re.search(r'^' + pattern, text)

    # Замена
    new_str = re.sub(pattern, repl, old_str)
    # В repl можно подставлять названия групп, например \1
    # Это позволяет заменять не все

## Функциональный и классовый интерфейсы

С модулем `re` можно работать в двух вариантах - функциональном и классовом. Я предпочитаю функциональный. Это исключительно вопрос вкуса.

    # Вариант 1
    match = exp.match(pattern, text)

    # Вариант 2
    exp = re.compile(pattern)
    exp.match(text)

## Рецепты

    # Working with word list
    if re.match(r'{0}(-{0})?'.format(r'|'.join(word_list)), word.lower()):
        pass

    # Partial substitution
    pattern = r'(\w)\s?=\s?(\d)'
    match = re.sub(pattern, r'\1 = \2', 'I have n=50 apples')

## Справка

```
Regular Expression Basics
.   Any character except newline
a   The character a
ab  The string ab
a|b a or b
a*  0 or more a's
\   Escapes a special character
Regular Expression Quantifiers
-   0 or more
*   1 or more
?   0 or 1
{2} Exactly 2
{2, 5}  Between 2 and 5
{2,}    2 or more
(,5}    Up to 5
Default is greedy. Append ? for reluctant.
Regular Expression Groups
(...)   Capturing group
(?P<Y>...)  Capturing group named Y
(?:...) Non-capturing group
\Y  Match the Y'th captured group
(?P=Y)  Match the named group Y
(?#...) Comment

Regular Expression Character Classes
[ab-d]  One character of: a, b, c, d
[^ab-d] One character except: a, b, c, d
[\b]    Backspace character
\d  One digit
\D  One non-digit
\s  One whitespace
\S  One non-whitespace
\w  One word character [a-zA-Z0-9_]
\W  One non-word character
Regular Expression Assertions
^   Start of string
\A  Start of string, ignores m flag
$   End of string
\Z  End of string, ignores m flag
\b  Word boundary
\B  Non-word boundary
(?=...) Positive lookahead
(?!...) Negative lookahead
(?<=...)    Positive lookbehind
(?<!...)    Negative lookbehind
(?()|)  Conditional

Regular Expression Flags
i   Ignore case
m   ^ and $ match start and end of line
s   . matches newline as well
x   Allow spaces and comments
L   Locale character classes
u   Unicode character classes
(?iLmsux)   Set flags within regex
Regular Expression Special Characters
\n  Newline
\r  Carriage return
\t  Tab
\YYY    Octal character YYY
\xYY    Hexadecimal character YY
Regular Expression Replacement
\g<0>   Insert entire match
\g<Y>   Insert match Y (name or number)
\Y  Insert group numbered Y
```
