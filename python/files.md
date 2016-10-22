# Работа с файлами
Date: 2016-03-01

## Открытие файла

    :::python
    f = open('file1.txt', 'r')
        f.close() 

    with open('file2.txt', 'w') as f:
        pass

*Использование with - хорошая практика. Это предотвращает возможность ошибки, если код выполняется не на CPython.*

### Типы открытия файлов
    
    :::python
    'r'     # Read. Чтение файла - по умолчанию
    'w'     # Write. Создать пустой файл и записывать в него. Если файл уже существует, он будет стерт
    'a'     # Append. Дозапись файла
    'r+'    # Чтение и запись

## Чтение и запись

    :::python
    f.read()                 # Полное чтение файла
    
    f.readline()             # Построчное чтение
    
    for line in f:           # Построчное чтение
        line
    
    f.write('sample text\n') # Запись

## Работа с файловой системой

```python
# Копировать файл
from shutil import copyfile
copyfile(src, dst)

# Содержание директории
from os import listdir
for fn in listdir(path):
    print path

# Операции с именем файла
from os.path import join, splitext
join(dir_path, filename)
filename, ext = splitext(full_filename)

```
