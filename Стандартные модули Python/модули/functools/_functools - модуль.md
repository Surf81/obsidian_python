# Модуль `functools`
***

### `wraps()`:
#декоратор

Является универсальным декоратором функции для сохранением ее атрибутов. Применяетя к функции-обертке

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
	@functools.wraps(func)        # 
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