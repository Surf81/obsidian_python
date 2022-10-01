# Класс `namedtuple` модуля [collections](_collections%20-%20модуль.md)
#namedtuple #кортеж  [почитать](https://antonz.ru/namedtuple/)
***
Класс `namedtuple` является наследуемым от  [tuple](../../../Встроенные%20возможности%20Python/tuple/_tuple%20-%20тип%20данных.md) и содержит все его методы и возможности. Поддерживает распаковку и срезы
Дополнительно содержит возможность обращения к значениям не только через индексы, но и через именованные поля.

```python
from collections import namedtuple 
Point = namedtuple('Point', ['x', 'y']) # объявляем тип Point именованного кортежа 

point = Point(3, 7)     # создаем именованный кортеж Point 
point = Point(y=7, x=3) # можно использовать именованные аргументы

print(point)                        # Point(x=3, y=7)
print(point.x, point.y)             # 3 7
print(point[0], point[1])           # 3 7
print(type(point))                  # <class '__main__.Point'>
```

## Методы класса `namedtuple`
***
- **[namedtuple()](#namedtuple)** - создание объекта именованного кортежа
- **[\_asdict()](#_asdict)** - преобразование именованного кортежа в словарь
- **[\_make()](#_make)** - создает именованный кортеж из любого итерируемого объекта
- **[\_replace()](#_replace)** - изменение именованного кортежа

## Атрибуты объекта класса `namedtuple`
- - -
- **\_fields** - возвращает кортеж имен полей именованного кортежа (можно создавать новые именованные кортежи на основании уже существующих)
- **\_field_defaults** - возвращает значения полей по умолчанию (если они есть) в виде словаря `dict`


### `namedtuple()`: 
выступает в роли **фабричной функции**, порождающей новые типы данных.

Сигнатура данной функции имеет вид: 

```python
namedtuple(typename, field_names, *, rename=False, defaults=None, module=None)
```

То есть функция принимает два обязательных параметра `typename` и `field_names` и три необязательных `rename`, `defaults`, `module`, имеющих значения по умолчанию `False`, `None`, `None` соответственно.
#### Параметры функции:
- `typename` - строка, отвечает за имя создаваемого типа
- `field_names` - названия полей. В качестве параметра `field_names` можно использовать: список, словарь, кортеж, строка, множество или итератор (map(), filter()...)
- `rename` - если установить в значение `True` 'неудачные' имена параметров переименуются в порядковые номера. Неудачные - совпадающие с ключевыми полями или повторяющиеся. Пригодится, например, если для имен параметров используем первую строку `csv` файла. **Пример применения ниже**
- `defaults` - кортеж или список со значениями по умолчанию. Если указаны не для всех полей, то будут установлены по порядку с конца. Пример ниже. Работает с `Python 3.7+`
- `module` - указание имени модуля результирующего именованного кортежа вместо `__main__`. Служит для возможности использования сериализации [pickle](../pickle/_pickle%20-%20модуль.md)

**Примечания**:	
>Если параметр `field_names` является словарем, в этом случае для полей именованного кортежа используются ключи словаря, поэтому в качестве значений можно указать, все что угодно.

```python
from collections import namedtuple

Point = namedtuple('Point', {'x': 0, 'y': 69})    # в качестве второго параметра передаем словарь
point =  Point(2, 4)
print(point)                                      # выводит Point(x=2, y=4)
```

>Если `field_names` является строкой поля указываются либо через символ пробела, либо разделяя их символом `,`

```python
from collections import namedtuple

Point = namedtuple('Point', 'x,y')    # в качестве второго параметра передаем строку
point =  Point(2, 4)
print(point)                          # выводит Point(x=2, y=4)
```

>Использовать в поле `field_names` множества для создания именованного кортежа не рекомендуется из-за негарантированного порядка элементов во множестве

>Пример применения параметра `rename`

```python
from collections import namedtuple

New_namedtuple  = namedtuple('MyType', 'x y x y class', rename=True)
p = New_namedtuple(10, 20, 30, 40, 50)

print(p)      # MyType(x=10, y=20, _2=30, _3=40, _4=50)
```

>Пример применения `defaults`

 ```python
from collections import namedtuple

New_namedtuple  = namedtuple('MyType', 'x y z a b', defaults=(1, 2))
p = New_namedtuple(10, 20, 30)

print(p)      # MyType(x=10, y=20, z=30, a=1, b=2)

```

>Пример использования `module`

```python
from collections import namedtuple 
Point = namedtuple('Point', ['x', 'y'], module='customtypes') 
point = Point(1, 2) 
print(type(point))     # <class 'customtypes.Point'>
```

### `_asdict()`:
Преобразование в словарь `dict()`. До версии `Python 3.8` возвращал `OrderedDict`
```python
from collections import namedtuple

New_namedtuple  = namedtuple('MyType', 'x y')
p = New_namedtuple(10, 20)
d = p._asdict()

print(d)      # {'x': 10, 'y': 20}
```

### `_make()`:
Создает именованный кортеж из итерируемого объекта (строки, словаря, списка, кортежа, итератора)
```python
from collections import namedtuple 
Person = namedtuple('Person', ['name', 'age', 'height']) 
timur = Person._make(['Timur', 29, 170]) 
print(timur)
```

### `_replace()`:
Быстрое изменение именованного кортежа
```python
from collections import namedtuple

New_namedtuple  = namedtuple('MyType', 'x y'
p = New_namedtuple(10, 20)
p = p._replace(x=100)

print(p)      # MyType(x=100, y=20)
```
