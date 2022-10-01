## Класс [`datetime`](datetime%20-%20класс.md) модуля [datetime](_datetime%20-%20модуль.md)
#datetime #дата #время
***
```python
import datetime

dt = datetime.datetime(year, month, day, hour=0, 
                      minute=0, second=0, microsecond=0, 
                      tzinfo=None, *, fold=0)
```

### Параметры:

Аргументы `year`, `month` и `day` обязательны. Аргумент `tzinfo` может быть `None` или экземпляром [подкласса datetime.tzinfo](tzinfo%20-%20класс.md) Остальные аргументы должны быть целыми числами:

-   `year` - год в пределах `MINYEAR <= year <= MAXYEAR`,
-   `month` - месяц в пределах `1 <= month <= 12`,
-   `day` - день в пределах `1 <= day <= n_day`, n_day - количество дней в данном месяце и году,
-   `hour=0` - часы в пределах `0 <= hour < 24`,
-   `minute=0` - часы в пределах `0 <= minute < 60`,
-   `second=0` - секунды в пределах `0 <= second < 60`,
-   `microsecond=0` - микросекунды в пределах `0 <= microsecond < 1000000`,
-   `tzinfo=None` - может быть `None` или экземпляром [подкласса datetime.tzinfo](tzinfo%20-%20класс.md). Так же смотрите [модуль zoneinfo](../zoneinfo/_zoneinfo%20-%20модуль.md) (добавлен в Python 3.9) - конкретная реализация часового пояса для поддержки базы данных часовых поясов IANA,
-   `fold=0` - `[0, 1]`. 0 - зимнее время 1 - летнее

Если задан аргумент вне этих диапазонов, вызывается исключение [`ValueError`](https://docs-python.ru/tutorial/vstroennye-iskljuchenija-interpretator-python/vstroennye-iskljuchenija/ "Исключения наследуемые от Exception в Python.").

### Возвращаемое значение:

-   объект даты и времени `datetime.datetime()`.

### Описание:

Класс `datetime()` модуля [datetime](_datetime%20-%20модуль.md) это отдельный объект, объединяющий всю информацию из объекта даты [datetime.date](date%20-%20класс.md)  и объекта времени [datetime.time](time%20-%20класс.md).

Атрибуты экземпляра класса `datetime.datetime()`, доступны только для чтения:

-   `dt.year` - возвращает год как целое число,
-   `dt.month` - возвращает месяц как число от 1 до 12 включительно,
-   `dt.day` - возвращает день от 1 до количества дней в данном месяце данного года,
-   `dt.hour` - возвращает час в диапазоне `range(24)`,
-   `dt.minute` - возвращает минуты в диапазоне `range(60)`,
-   `dt.second` - возвращает секунды в диапазоне `range(60)`,
-   `dt.microsecond` - возвращает секунды в диапазоне `range(1000000)`,
-   `dt.tzinfo` - возвращает объект, переданный в качестве аргумента `tzinfo` или `None`, если ничего не было передано.
-   `dt.fold` - возвращает зимнее 0 или летнее 1 время. Используется для устранения неоднозначности времени в момент перехода с зимнего на летнее время и обратно, когда смещение UTC для текущей зоны уменьшается или увеличивается.

### Способы создания объекта `datetime.datetime`:

-   [Текущая локальная дата и время](https://docs-python.ru/standart-library/modul-datetime-python/klass-datetime-modulja-datetime/#datetime.today) `datetime.datetime.today()`,
-   [Текущая локальная дата и время](https://docs-python.ru/standart-library/modul-datetime-python/klass-datetime-modulja-datetime/#datetime.now) `datetime.datetime.now()`,
-   [Текущая дата и время UTC](https://docs-python.ru/standart-library/modul-datetime-python/klass-datetime-modulja-datetime/#datetime.utcnow) `datetime.datetime.utcnow()`,
-   [Из `timestamp`](https://docs-python.ru/standart-library/modul-datetime-python/klass-datetime-modulja-datetime/#datetime.fromtimestamp) `datetime.datetime.fromtimestamp()`,
-   [Дата и время UTC из `timestamp`](https://docs-python.ru/standart-library/modul-datetime-python/klass-datetime-modulja-datetime/#datetime.utcfromtimestamp) `datetime.datetime.utcfromtimestamp()`,
-   [Из `datetime.date` + `datetime.time`](https://docs-python.ru/standart-library/modul-datetime-python/klass-datetime-modulja-datetime/#datetime.combine) `datetime.datetime.combine()`,
-   [Из строки ISO](https://docs-python.ru/standart-library/modul-datetime-python/klass-datetime-modulja-datetime/#datetime.fromisoformat) `datetime.datetime.fromisoformat()`,
-   [Из календарной даты ISO,](https://docs-python.ru/standart-library/modul-datetime-python/klass-datetime-modulja-datetime/#datetime.fromisocalendar) `datetime.datetime.fromisocalendar()`,
-   [Из строки](https://docs-python.ru/standart-library/modul-datetime-python/klass-datetime-modulja-datetime/#datetime.strptime) `datetime.datetime.strptime()`.

### [Методы объекта datetime](datetime%20-%20методы.md)
---

### Поддерживаемые операции `datetime.datetime()`:


(1) datetime2 = datetime1 + `timedelta`

(2) datetime2 = datetime1 - `timedelta`

(3) `timedelta` = datetime1 - datetime2

(4) datetime1 < datetime2



