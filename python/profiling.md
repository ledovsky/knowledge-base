# Профилирование

```
python -m cProfile -o file.prof file.py
python -m pstats file.prof

# Переходим в консоль pstats
sort cumtime
stats 20

```
