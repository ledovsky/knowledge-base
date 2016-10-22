# Настройка путей для каждого рабочего компьютера команды

```python
import platform
host = platform.node()

if host == 'ledovsky-laptop':
    raw_data_path = '../../raw_data/'
    data_path = '../../data/'
```
