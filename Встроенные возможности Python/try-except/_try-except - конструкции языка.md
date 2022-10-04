# Конструкция `try - except`
#tryexcept #конструкцииязыка
***
```python
try:
	# попытка
except (ExceptName1, ExceptName2, ExceptName3):
	# при наступлении одного из перечисленных исключений
except ExceptName:
	# при наступлении конкретного исключения
except (ExceptName1, ExceptName2) as Err:
	# запоминает вид исключения в переменной
except:
	# при наступлении любого, ранее не указанного исключения
else:
	# если ошибок не было и исключения не возникали
finally:
	# вызывается в любом случае: и если были исключения и если не были
```

Секция `finally` исполняется всегда, даже если до нее был вызван `return`, `break`, `continue` При этом `finally` вызывается первым
```python
def func():
    try:
        return 10
    finally:
        print('Выполняется блок finally!')

print(func()) # выводит:  Выполняется блок finally!
              #           10

def func(): 
try: 
	return 10 
finally: 
	return 20 

print(func())  # выведет 20
```

Блок else не выполняется если было вызвано прерывание или возврат
```python
def f(): 
try: 
	return 10 
except: 
	pass 
else: 
	return 20 

print(f())     # выведет 10
```

### `raise`:
Вызов исключения вручную
```python
raise # неименованное исключение - улавливается только блоком except:
raise KeyError  # страндартное исключение
raise ValueError("Несоответствующее значение") # с комментарием
```

Создание собственных видов исключений:
```python
class MyError(Exception): 
	print("Это проблема") 

raise MyError("ошибка MyError")
```

## Список стандартных исключений
***
**Дерево встроенных исключений**:

```no-highlight
BaseException
 +-- SystemExit
 +-- KeyboardInterrupt
 +-- GeneratorExit
 +-- Exception
      +-- StopIteration
      +-- StopAsyncIteration
      +-- ArithmeticError
      |    +-- FloatingPointError
      |    +-- OverflowError
      |    +-- ZeroDivisionError
      +-- AssertionError
      +-- AttributeError
      +-- BufferError
      +-- EOFError
      +-- ImportError
           +-- ModuleNotFoundError
      +-- LookupError
      |    +-- IndexError
      |    +-- KeyError
      +-- MemoryError
      +-- NameError
      |    +-- UnboundLocalError
      +-- OSError
      |    +-- BlockingIOError
      |    +-- ChildProcessError
      |    +-- ConnectionError
      |    |    +-- BrokenPipeError
      |    |    +-- ConnectionAbortedError
      |    |    +-- ConnectionRefusedError
      |    |    +-- ConnectionResetError
      |    +-- FileExistsError
      |    +-- FileNotFoundError
      |    +-- InterruptedError
      |    +-- IsADirectoryError
      |    +-- NotADirectoryError
      |    +-- PermissionError
      |    +-- ProcessLookupError
      |    +-- TimeoutError
      +-- ReferenceError
      +-- RuntimeError
      |    +-- NotImplementedError
      |    +-- RecursionError
      +-- SyntaxError
      |    +-- IndentationError
      |         +-- TabError
      +-- SystemError
      +-- TypeError
      +-- ValueError
      |    +-- UnicodeError
      |         +-- UnicodeDecodeError
      |         +-- UnicodeEncodeError
      |         +-- UnicodeTranslateError
      +-- Warning
           +-- DeprecationWarning
           +-- PendingDeprecationWarning
           +-- RuntimeWarning
           +-- SyntaxWarning
           +-- UserWarning
           +-- FutureWarning
           +-- ImportWarning
           +-- UnicodeWarning
           +-- BytesWarning
           +-- ResourceWarning
```

-   `IndexError`: возникает, когда индекс (например, для элемента списка) указан неправильно (выходит за границы допустимого диапазона)
-   `KeyError`: возникает при неверно указанном ключе словаря
-   `NameError`: возникает, если не удается найти переменную с некоторым названием
-   `SyntaxError`: возникает при наличии в исходном коде синтаксических ошибок
-   `TypeError`: возникает при несоответствии типов, когда для обработки требуется значение определенного типа, а передается значение другого типа
-   `FileNotFoundError`: возникает при открытии несуществующего файла
-   `ValueError`: возникает, когда в функцию передается аргумент с неподдерживаемым значением
-   `ZeroDivisionError`: возникает при попытке выполнить деление на ноль