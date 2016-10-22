# Работа с датами и временем
Date: 2016-02-20

## Создание объекта datetime

    :::python
    from datetime import datetime, date, time
    
    d = date(2000, 1, 1)
    t = time(12, 30)
    dt1 = datetime.combine(d, t)
    dt2 = datetime(2000, 1, 1, 12, 30)
    dt3 = datetime.now()
    dt4 = datetime.strptime("21.11.06 16:30", '%d.%m.%y %H:%M')
    dt5 = datetime.fromtimestamp(unix_timestamp)

## Получение данных из объекта datetime 

    :::python
    
    # as attribute
    dt.year
    dt.month
    # ..
    
    # as string
    dt.strftime('%d.%m.%y %H:%M')

## Параметры strptime и strftime

[Ссылка на документацию](https://docs.python.org/2/library/datetime.html#strftime-and-strptime-behavior)

    :::python
    %Y     # Год (2000)
    %y     # Год (00)
    
    %m     # Месяц (01)
    %B     # Месяц (January)
    %b     # Месяц (Jan)
    
    %d     # День (01)
    
    %A     # День недели (Monday)
    %a     # День недели (Mon)
    
    %H     # Часы (24)
    %I     # Часы (12)
    %p     # Часы (pm)
    
    %M     # Минуты (60)
    %S     # Секунды (60)
