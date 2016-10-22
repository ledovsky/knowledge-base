# Измерение времени работы кода

## Функция time

    :::python
    start_time = time.time()
    # your code
    print '--- {:.2f} seconds ---'.format(time.time() - start_time)

## Декоратор для измерения времени

    :::python
    import time
    def timer(f):
        def func_wrapper(*args, **kwargs):
            t = time.time()
            print "Start function: {}".format(f.__name__)
            res = f(*args, **kwargs)
            print "Function completed: {}. Time elapsed: {:.3f}s".format(f.__name__, (time.time()-t))
            return res
    
        return func_wrapper

## Timeit - измерение времени действия одной строки кода

Библиотека нужна, чтобы сравнить производительность разных конструкций, выполняющих одно и то же действие.

![Ссылка на документацию](https://docs.python.org/2/library/timeit.html)
