# Перенос строк в коде Python

Все, что находится внутри скобок можно переносить без какого-либо дополнительного синтаксиса

    my_class.func(arg1, arg2,
                  arg3, arg4)

    my_list  = [
        'entry 1',
        'entry 2',
        'entry 3'
    ]

    'my good string'.replace(
        'good', 'bad')

    if (5 > 3 and
            3 > 1):
        print "True"

Также можно использовать разделитель `\`

    'my good string'.\
        replace('good', 'bad')


Строки можно переносить с помощью заключения их в скобки

    my_string = (
        'part 1'
        'part 2'
        'part 3'
    )

