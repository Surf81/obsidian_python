# Модуль `functools`
***
- [partial function args](#partial%20function%20args)

### `partial(function, *args)`:
Функция `partial()` возвращает `partial` объект, который при вызове ведет себя как функция c подставленными в нее значениями `args`

### `reduce(function, iterable, inintializer)`:
#### Параметры:

-   `function` - пользовательская функция, принимающая 2 аргумента,
-   `iterable` - итерируемая последовательность,
-   `initializer` - начальное значение.

#### Возвращаемое значение:
-   требуемое единственное значение.

#### Описание:

Функция `reduce()` модуля `functools` кумулятивно применяет функцию `function` к элементам итерируемой `iterable` последовательности, сводя её к единственному значению.

### `wraps()`:
#декоратор

Является универсальным декоратором функции для сохранения ее атрибутов. Применяетя к функции-обертке

При использовании обычного декоратора, функция теряет свои атрибуты `__name__` и `__doc__`
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