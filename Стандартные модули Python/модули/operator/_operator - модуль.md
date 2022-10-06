# Модуль `operator`
#operator #инструменты #операторы 
***

>### [Альтернативные операторы](#Альтернативные%20операторы)
>### [Общий интерфейс поиска атрибутов и элементов](#Общий%20интерфейс%20поиска%20атрибутов%20и%20элементов)


## Альтернативные операторы

Функции, связанные со встроенными операторами языка программирования Python.

### Таблица соответствия методов модуля `operator`

|Операция|Синтаксис|Функция модуля `operator`|
|--------|---------|-------|
|сложение|`a + b`|`add(a, b)`|
|сложение на месте|`a += b`|`iadd(a, b)` (для изменяемых объектов)|
|конкатенация|`seq1 + seq2`|`concat(seq1, seq2)`|
|тест на содержание|`obj in seq`|`contains(seq, obj)`|
|деление|`a / b`|`truediv(a, b)`|
|целочисленное деление|`a // b`|`floordiv(a, b)`|
|побитовое AND|`a & b`|`and_(a, b)`|
|побитовое эксклюзивное OR|`a ^ b`|`xor(a, b)`|
|побитовая инверсия|`~ a`|`invert(a)`|
|побитовое OR|`a \| b`|`or_(a, b)`|
|возведение в степень|`a ** b`|`pow(a, b)`|
|тождественность|`a is b`|`is_(a, b)`|
|отрицание тождественности|`a is not b`|`is_not(a, b)`|
|присвоение по индексу|`obj[k] = v`|`setitem(obj, k, v)`|
|удаление по индексу|`del obj[k]`|`delitem(obj, k)`|
|индексирование|`obj[k]`|`getitem(obj, k)`|
|смещение влево|`a << b`|`lshift(a, b)`|
|модуль|`a % b`|`mod(a, b)`|
|умножение|`a * b`|`mul(a, b)`|
|умножение на месте|`a *= b`|`imul(a, b)` (для изменяемых объектов)|
|умножение матриц|`a @ b`|`matmul(a, b)`|
|отрицание (арифметика)|`- a`|`neg(a)`|
|отрицание (логическое)|`not a`|`not_(a)`|
|положительный|`+ a`|`pos(a)`|
|сдвиг вправо|`a >> b`|`rshift(a, b)`|
|присвоение среза|`seq[i:j] = values`|`setitem(seq, slice(i, j), values)`|
|удаление среза|`del seq[i:j]`|`delitem(seq, slice(i, j))`|
|получение среза|`seq[i:j]`|`getitem(seq, slice(i, j))`|
|форматирование строк|`s % obj`|`mod(s, obj)`|
|вычитание|`a - b`|`sub(a, b)`|
|вычитание на месте|`a -= b`|`isub(a, b)` (для изменяемых объектов)|
|проверка на True|`obj`|`truth(obj)`|
|меньше|`a < b`|`lt(a, b)`|
|меньше или равно|`a <= b`|`le(a, b)`|
|равенство|`a == b`|`eq(a, b)`|
|неравно|`a != b`|`ne(a, b)`|
|больше|`a >= b`|`ge(a, b)`|
|больше или равно|`a > b`|`gt(a, b)`|

## Общий интерфейс поиска атрибутов и элементов

### `attrgetter(*atribute: str)`:
#сортировка #фильтрация #итераторы 

Доступ к элементам по имени атрибута(ов)

Создает "шаблон подстановки" значения атрибута, актуального для набора объектов при обработке последовательностей (например при сотрировке)
```python
import operator
class S:
    def __init__(self, islower: bool) -> None:
        self.islower: bool = islower


    def __repr__(self) -> str:
        return f"Student(islower={self.islower})"

s = [S(True), S(False)]  # в списке любые объекты, имеющие атрибут islower
get_attr = operator.attrgetter("islower")
print(list(filter(get_attr, s)))
```


### `itemgetter(*index: int)`:
#сортировка #фильтрация #итераторы 

Доступ к элементам по индексу(ам)
```python
import operator
s = [(0, 'oleg', 'ivanov'), (1, 'ivan', 'petrov'), (2, 'fedor', 'stepanov'), 
	 (3, 'alex', 'ivanov')]

get_index = operator.itemgetter(2, 1)
print(sorted(s, key=get_index)) # сортировка по фамилии и имени
								# [(3, 'alex', 'ivanov'), (0, 'oleg', 'ivanov'),
								# (1, 'ivan', 'petrov'), (2, 'fedor', 'stepanov')]

get_index = operator.itemgetter(1)
print(sorted(s, key=get_index)) # сортировка по имени
                                # [(3, 'alex', 'ivanov'), (2, 'fedor', 'stepanov'),
                                # (1, 'ivan', 'petrov'), (0, 'oleg', 'ivanov')]
```


### `methodcaller(method: str, *args, **kwargs)`:
#итераторы

Доступ к методам класса. Идея состоит в том, чтобы создать вызываемый объект, который вызывает метод для своего операнда
```python
import operator

s = 'AsdOkxVmNW'

get_method = operator.methodcaller("islower")
print(sorted(s, key=get_method))

# выведет

['A', 'O', 'V', 'N', 'W', 's', 'd', 'k', 'x', 'm']
```