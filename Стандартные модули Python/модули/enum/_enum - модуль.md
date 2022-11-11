# Модуль `enum`
#enum #перечисления
***

Модуль определяет четыре класса перечисления, которые могут использоваться для определения уникальных множеств имён и значений: [`Enum`](https://digitology.tech/docs/python_3/library/enum.html#enum.Enum "enum.Enum"), [`IntEnum`](https://digitology.tech/docs/python_3/library/enum.html#enum.IntEnum "enum.IntEnum"), [`Flag`](https://digitology.tech/docs/python_3/library/enum.html#enum.Flag "enum.Flag") и [`IntFlag`](https://digitology.tech/docs/python_3/library/enum.html#enum.IntFlag "enum.IntFlag"). Он также определяет один декоратор, [`unique()`](https://digitology.tech/docs/python_3/library/enum.html#enum.unique "enum.unique") и один вспомогательный класс — [`auto`](https://digitology.tech/docs/python_3/library/enum.html#enum.auto "enum.auto").

## _class_ `Enum`

Базовый класс для создания перечисляемых констант. Альтернативный синтаксис построения см. в разделе [Функциональный API](https://digitology.tech/docs/python_3/library/enum.html#api).

## _class_ `IntEnum`

Базовый класс для создания перечисляемых констант, которые также являются подклассами [`int`](https://digitology.tech/docs/python_3/library/functions.html#int "int").

## _class_ `IntFlag`

Базовый класс для создания нумерованных констант, которые можно комбинировать с помощью побитовых операторов, не теряя своего членства в [`IntFlag`](https://digitology.tech/docs/python_3/library/enum.html#enum.IntFlag "enum.IntFlag"). Поля [`IntFlag`](https://digitology.tech/docs/python_3/library/enum.html#enum.IntFlag "enum.IntFlag") также являются подклассами [`int`](https://digitology.tech/docs/python_3/library/functions.html#int "int").

## _class_ `Flag`

Базовый класс для создания нумерованных констант, которые можно комбинировать с помощью побитовых операций без потери принадлежности к [`Flag`](https://digitology.tech/docs/python_3/library/enum.html#enum.Flag "enum.Flag").

## `unique`()

Декоратор класса Enum, который обеспечивает привязку только одного имени к любому значению.

## _class_ `auto`

Экземпляры заменяются соответствующим значением для полей Enum. Начальное значение начинается с 1.