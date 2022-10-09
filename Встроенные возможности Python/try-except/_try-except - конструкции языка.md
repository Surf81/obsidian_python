# Конструкция `try - except`
#tryexcept #исключения #конструкцииязыка
***
```python
try:
	# попытка
except (ExceptName1, ExceptName2, ExceptName3):
	# при наступлении одного из перечисленных исключений
except ExceptName:
	# при наступлении конкретного исключения
except (ExceptName1, ExceptName2) as Err:
	# запоминает вид исключения в переменной Err
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


### `assert`:
Проверяет истинность утверждений. При неисполнении вызывает исключение `AssertionError`
>assert <утверждение>, <сообщение>

**Примечание:** Оператор `assert` — это средство отладки, а не механизм обработки ошибок времени выполнения программы (исключений). Цель использования оператора `assert` состоит в том, чтобы позволить разработчикам как можно скорее найти вероятную первопричину ошибки. Если в программе ошибки нет, то исключение `AssertionError` никогда не должно возникнуть. В связи с этим не следует писать код, который явно обрабатывает исключения `AssertionError` с помощью конструкции `try-except`

### `raise`:
Вызов исключения вручную
```python
raise # неименованное исключение - улавливается только блоком except:
raise KeyError  # страндартное исключение
raise ValueError(*args) # с комментарием (несколько параметров передадутся в виде кортежа, один - сам по себе)
```
Приведенный ниже код выводит:
```python
try:
    raise ValueError('Ой', 'Произошла ошибка')
except ValueError as e:
    print(e)        #  ('Ой', 'Произошла ошибка')
    print(e.args)   #  ('Ой', 'Произошла ошибка')
```

Создание собственных видов исключений:
```python
class MyError(Exception): 
	print("Это проблема") 

raise MyError("ошибка MyError")
```
'Пробрасывание' исключения
```python
try: х = 1 / 0 
except Exception as err: 
	print(err) # каким-то образом обработали перехваченное исключение 
	raise # пробрасываем исключение выше
```


### `issubclass()`:
Проверка на вложенность в [Деревe встроенных исключений](#Дерево%20встроенных%20исключений)
```python
issubclass(ZeroDivisionError, ArithmeticError) # True
```

## Список стандартных исключений
#exceptions #exceptionlist
***
### **Дерево встроенных исключений**:

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