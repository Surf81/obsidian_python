# Модуль `pickle`
#pickle #файлы 
***
Модуль `pickle` может сериализовывать:

-   все встроенные типы данных (`bool, int, float, complex, str, None`)
-   cписки, кортежи, словари и множества, содержащие любую комбинацию встроенных типов данных
-   cписки, кортежи, словари и множества, содержащие любую комбинацию списков, кортежей, словарей и множеств
-   функции (кроме lambda), классы и экземпляры классов

## Классы и методы модуля `pickle`
***
- **[dump()](#dump)** - сериализация в бинарный формат и запись в файл
- **[dumps()](#dumps)** - возвращает сериализованный объект в формате `bytes`
- **[load()](#load)** - чтение из файла и дерериализация данных
- **[loads()](#loads)** - десериализует объект `bytes` в исходный формат


### `dump()`:
Сериализация данных в бинарный формат и запись в файл
```python
import pickle 
obj = {'Python': 1991, 'Java': 1995, 'C#': 2002} 
with open('file.pkl', 'wb') as file:  #файл открывается в бинарном виде
	pickle.dump(obj, file)
```

### `dumps()`:
Сериализация данных в бинарный формат (тип данных `bytes`)
```python
import pickle 
obj = {'Python': 1991, 'Java': 1995, 'C#': 2002} 
binary_obj = pickle.dumps(obj)
```

### `load()`:
Чтение из файла и десериализация данных
```Python
import pickle 
with open('file.pkl', 'rb') as file: #  файл открывается в бинарном виде
	obj = pickle.load(file) 
	print(obj)
```

### `loads()`:
Принимает объект типа `bytes` и десериализует в исходный формат
```python
import pickle 
obj = {'Python': 1991, 'Java': 1995, 'C#': 2002} 
binary_obj = pickle.dumps(obj) 
new_obj = pickle.loads(binary_obj)
```
