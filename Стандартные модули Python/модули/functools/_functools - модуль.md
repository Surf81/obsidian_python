# Модуль `functools`
***
## Методы класса `functools` модуля `functools`
- **[partial(function, args, kwargs)](#partial%20function%20args%20kwargs)** - частичное применение функции
- **[reduce(function, iterable, inintializer)](#reduce%20function%20iterable%20inintializer)** - аккумулятор вычислений
- **[update_wrapper(wrapper, wrapped)](#update_wrapper%20wrapper%20wrapped)** - обновление атрибутов функции-обертки. 
- **[wraps()](#wraps)** - универсальный декоратор

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