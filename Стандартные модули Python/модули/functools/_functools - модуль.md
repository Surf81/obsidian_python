# Модуль `functools`
***
## Методы класса `functools` модуля `functools`
- **[lru_cache](#lru_cache)** - декоратор кеширования вычисляемых значений функции
- **[partial(function, args, kwargs)](#partial%20function%20args%20kwargs)** - частичное применение функции
- **[reduce(function, iterable, inintializer)](#reduce%20function%20iterable%20inintializer)** - аккумулятор вычислений
- **[update_wrapper(wrapper, wrapped)](#update_wrapper%20wrapper%20wrapped)** - обновление атрибутов функции-обертки. 
- **[wraps()](#wraps)** - декоратор сохранения атрибутов функции

### `lru_cache()`:
Декоратор функции для кеширования результатов выполнения функции в соответствии со стратегией очищения стека Least Recently Used (из стека кэша удаляются наиболее долго не использованные значения)

При декорировании функций с помощью декоратора `lru_cache` можно использовать следующие аргументы:
-   `maxsize=128` — максимальный размер кэша (тип `int`)
-   `typed=False` — как кэшировать при разных типах аргументов (тип `bool`)

Если для параметра `maxsize` установлено значение `None`, то кэш может расти без ограничений.

Если для `typed` задано значение `True`, то аргументы функций разных типов будут кэшироваться отдельно. Например, `f(3)` и `f(3.0)` будут рассматриваться как отдельные вызовы с разными результатами. Если для `typed` задано значение `False`, то вызовы будут рассматриваться как одинаковые.

```python
from functools import lru_cache 

@lru_cache           # до версии 3.8 нужно указывать со скобками 
def fibonacci(n): 
	if n <= 2: 
		return 1 
	else: 
		return fibonacci(n - 1) + fibonacci(n - 2)
```

#### Дополнительные методы декоратора `lru_cache`

##### `cache_info()`:
Чтобы помочь измерить эффективность кэша и настроить параметр `maxsize`, декорированная функция имеет метод `cache_info()`, который возвращает именованный кортеж, показывающий `hits`, `misses`, `maxsize` и `currsize`.

Мы можем использовать информацию, возвращаемую `cache_info()`, чтобы понять, как работает кэш, и настроить его, чтобы найти подходящий баланс между скоростью работы и объемом памяти:

-   `hits` – количество значений, которые `lru_cache` вернул непосредственно из памяти, поскольку они присутствовали в кэше
-   `misses` – количество значений, которые были вычислены, а не взяты из памяти
-   `maxsize` – это размер кэша, который мы определили, передав его декоратору
-   `currsize` – текущий размер кэша

##### `cache_clear()`:
Очистка кэша

### `partial(function, *args, **kwargs)`:
Функция `partial()` возвращает `partial` объект, который при вызове ведет себя как функция c подставленными в нее значениями `args`

`partial` объекты содержат три полезных атрибута:
-   `func` — исходная функция
-   `args` — зафиксированные позиционные аргументы (тип `tuple`)
-   `keywords` — зафиксированные именованные аргументы (тип `dict`)

```python
from functools import partial

def multiply(a, b):
    return a * b

double = partial(multiply, 2)
triple = partial(multiply, 3)

print(double(5))        # 2 * 5
print(triple(10))       # 3 * 10
```

В указанном случае `partial` объекты `double` и `triple` ведут себя как функция `multiply()`, которой в качестве первого аргумента передали число 2 в первом случае и 3 во втором. 

```python
from functools import partial 
basetwo = partial(int, base=2) 

print(basetwo('101'))    # выведет 5 (перевод из двоичного счисления)
```

### `reduce(function, iterable, inintializer)`:
#### Параметры:

-   `function` - пользовательская функция, принимающая 2 аргумента,
-   `iterable` - итерируемая последовательность,
-   `initializer` - начальное значение.

#### Возвращаемое значение:
-   требуемое единственное значение.

#### Описание:

Функция `reduce()` модуля `functools` кумулятивно применяет функцию `function` к элементам итерируемой `iterable` последовательности, сводя её к единственному значению.

### `update_wrapper(wrapper, wrapped)`:
Обновляет информацию атрибутов функции `wrapper`, взятые из `wrapped`
#### Параметры:
-   `wrapper` - функция-обертка,
-   `wrapped` - исходная функция,
-   `assigned` - кортеж значений. Какие атрибуты `wrapped` присваиваются `wrapper`. По умолчанию равно константе `WRAPPER_ASSIGNMENTS` - присваивает функции обертке `__module__` , `__name__`, `__qualname__`, `__annotations__` и `__doc__` 
-   `updated` - кортеж значений. Какие атрибуты `wrapper` обновляются из `wrapped`. По умолчанию равно константе  `WRAPPER_UPDATES` - обновляет в функции обертке `__dict__`

```python
import functools

def add_attrs(a=''):
    def decorator(func):
        def wrapper(*args, **kwargs):
            print(a)
            return func(*args, **kwargs)
        return wrapper
    return decorator


def myfunc(x, y=1):
    """Описание функции myfunc()"""
    print(x, y)

new_f = add_attrs(a='---------')(myfunc)
new_f2 = functools.partial(myfunc, y=10)

functools.update_wrapper(new_f, myfunc)   # применение к функции-декоратору
functools.update_wrapper(new_f2, myfunc)  # применение к объекту `partial`

new_f(5, 5)
print(new_f.__doc__)     # Описание функции myfunc()
print(new_f.__name__)    # myfunc

new_f2(15)
print(new_f2.__doc__)    # Описание функции myfunc()
print(new_f2.__name__)   # myfunc
```


### `wraps()`:
#декоратор

Является универсальным декоратором функции для сохранения ее атрибутов. Применяетя к функции-обертке. Данный декоратор использует функцию `update_wrapper()` для копирования атрибутов `__name__` и `__doc__`

При использовании обычного декоратора, функция теряет свои атрибуты `__name__` и `__doc__`. `wraps()` позволяет их сохранить
```python
def bold(func): 
	def wrapper(*args, **kwargs): 
	return '<b>' + func(*args, **kwargs) + '</b>' 
return wrapper 

@bold 
def greet(name): 
	'''Функция приветствия пользователя.''' 
	return f'Hello {name}!' 

print(greet.__name__)   # выведет wrapper
print(greet.__doc__)    # выведет None
```

Пример использования `wraps`:
```python
import functools 
def bold(func): 
	@functools.wraps(func)        # применяется как декоратор к функции-обертке
	def wrapper(*args, **kwargs): 
		return '<b>' + func(*args, **kwargs) + '</b>' 
	return wrapper 

@bold 
def greet(name): 
	'''Функция приветствие пользователя.''' 
	return f'Hello {name}!' 

print(greet.__name__)   # выведет greet
print(greet.__doc__)    # выведет Функция приветствие пользователя.
```