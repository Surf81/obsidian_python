## Методы объекта [`datetime`](datetime%20-%20класс.md) модуля [datetime](_datetime%20-%20модуль.md)
#datetime 
***
-   [dt.date()](#dt.date)  - Получить объект `datetime.date()`,
-   [dt.time()](#dt.time) - Получить объект `datetime.time()` без `tzinfo`,
-   [dt.timetz()](#dt.timetz) - Получить объект `datetime.time()` с `tzinfo`,
-   [dt.replace()](#dt%20replace%20year%20self%20year%20month%20self%20month%20day%20self%20day%20hour%20self%20hour%20minute%20self%20minute%20second%20self%20second%20microsecond%20self%20microsecond%20tzinfo%20self%20tzinfo%20fold%200) - Изменить значения элементов даты и времени,
-   **[dt.strftime()](#dt.strftime)** - Получить дату в пользовательском формате,
-   [dt.astimezone()](#dt%20astimezone%20tz%20None) - Изменить атрибут `tzinfo`,
-   [Получить смещение времени UTC в виде `timedelta`](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.utcoffset) `dt.utcoffset()`,
-   [Получить смещение летнего времени](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.dst) `dt.dst()`,
-   [Получить название часового пояса](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.tzname) `dt.tzname()`,
-   [Получить кортеж структуры времени типа `time.localtime()`](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.timetuple) `dt.timetuple()`,
-   [Получить кортеж структуры времени по UTC](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.utctimetuple) `dt.utctimetuple()`,
-   [Григорианский порядковый номер даты](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.toordinal) `dt.toordinal()`,
-   [Получить метку времени `timestamp`](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.timestamp) `dt.timestamp()`,
-   [Получить день недели где понедельник = 0](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.weekday) `dt.weekday()`,
-   [Получить день недели где понедельник = 1](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.isoweekday) `dt.isoweekday()`,
-   [Получить кортеж (год, номер недели, день недели)](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.isocalendar) `dt.isocalendar()`,
-   [Получить строку с датой и временем в формате ISO 8601](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.isoformat) `dt.isoformat()`,
-   [Получить строку с датой и временем](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.__str__) `dt.__str__()`,
-   [Получить другую строку с датой и временем](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.ctime) `dt.ctime()`,


---

### `dt.date()`:

Метод `dt.date()` возвращает объект [datetime.date()](date%20-%20класс.md) с тем же годом, месяцем и днем.
```python
import datetime
dt = datetime.datetime.now()
dt.date()
# datetime.date(2020, 5, 6)
```

### `dt.time()`:

Метод `dt.time()` возвращает объект [datetime.time()](time%20-%20класс.md) с тем же часом, минутой, секундой, микросекундой, при этом параметр `tzinfo` будет равен `None`. Смотрите также [метод `datetime.timetz()`](#dt.timetz).

```python
import datetime
dt = datetime.datetime.now()
dt.time()
# datetime.time(9, 47, 7, 560533)
```

### `dt.timetz()`:

Метод `dt.timetz()` возвращает объект [`datetime.time()`](https://docs-python.ru/standart-library/modul-datetime-python/klass-time-modulja-datetime/ "Класс time() модуля datetime в Python.") с такими же атрибутами часа, минуты, секунды, микросекунды и `tzinfo`. Смотрите также [метод `datetime.time()`](#dt.time).

```python
import datetime
dt = datetime.datetime.now()
dt.timetz()
# datetime.time(9, 47, 7, 560533)
```

### `dt.replace(year=self.year, month=self.month, day=self.day, hour=self.hour, minute=self.minute, second=self.second, microsecond=self.microsecond, tzinfo=self.tzinfo, * fold=0)`:

Метод `dt.replace()` возвращает новый объект `datetime.datetime()` с теми же атрибутами, за исключением тех атрибутов, которым даны новые значения в зависимости от того, какие ключевые аргументы указаны.

Обратите внимание, что можно указать `tzinfo=None` для [создания "наивного"](https://docs-python.ru/standart-library/modul-datetime-python/ "Модуль datetime в Python, работа с датой и временем.") объекта `datetime.datetime()` из "осведомленного" без преобразования данных даты и времени.

```python
import datetime
dt = datetime.datetime.now()
dt
# datetime.datetime(2020, 5, 6, 9, 56, 14, 920298)
dt.replace(year=2022, month=6, hour=15)
# datetime.datetime(2022, 6, 6, 15, 56, 14, 920298)
```

### `dt.strftime(format)`:

Метод `dt.strftime()` возвращает строку, представляющую дату и время, управляемую явной строкой формата.

Полный список директив форматирования смотрите в разделе ["Поведение методов `strftime()` и `strptime()` модуля `datetime`"](Форматирование%20strftime()%20strptime().md).

```python
import datetime
dt = datetime.datetime.now()
dt.strftime('%H:%M - %m.%d.%Y года')
# '09:56 - 05.06.2020 года'
dt.strftime('%H часов %M минут %m.%d.%Y года')
# '09 часов 56 минут 05.06.2020 года'
dt.strftime('%m/%d/%y')
# '05/06/20'
dt.strftime('%Y-%m-%d')
# '2020-05-06'
```

### `dt.astimezone(tz=None)`:

Метод `dt.astimezone()` возвращает новый объект [`datetime.datetime()`](https://docs-python.ru/standart-library/modul-datetime-python/klass-datetime-modulja-datetime/ "Класс datetime() модуля datetime в Python.") с новым атрибутом `tzinfo`, скорректировав данные даты и времени таким образом, чтобы результатом было то же время UTC, но по местному времени `tz`.

-   Если указан аргумент `tz`, то он должен быть экземпляром подкласса [`datetime.tzinfo()`](https://docs-python.ru/standart-library/modul-datetime-python/klass-tzinfo-modulja-datetime/ "Класс tzinfo() модуля datetime в Python."), а его методы `tzinfo.utcoffset()` и `tzinfo.dst()` не должны возвращать `None`. Если `self` - "наивно", то предполагается, что оно представляет время в часовом поясе системы.
-   Если вызывается без аргументов или с `tz=None`, то системный часовой пояс местного времени принимается за целевой часовой пояс. Атрибут `.tzinfo` преобразованного экземпляра `datetime.datetime()` будет установлен на экземпляр [`datetime.timezone()`](https://docs-python.ru/standart-library/modul-datetime-python/klass-timezone-modulja-datetime/ "Класс timezone() модуля datetime в Python.") с именем зоны и смещением, полученными из ОС.
    
    >>> import datetime
    >>> dt = datetime.datetime.now()
    >>> dt
    # datetime.datetime(2020, 5, 6, 9, 56, 14, 920298)
    >>> dt.astimezone()
    # datetime.datetime(2020, 5, 6, 9, 56, 14, 920298, \
    # tzinfo=datetime.timezone(datetime.timedelta(0, 10800), 'MSK'))
    
-   Если `self.tzinfo` равно `tz`, а `self.astimezone(tz)` равно `self`: настройка даты или времени не выполняется. В противном случае результатом является местное время в часовом поясе `tz`, представляющее то же время в формате UTC, что и в `self`: после `astz = dt.astimezone(tz)`, `astz - astz.utcoffset()` будет иметь те же данные о дате и времени, что и `dt - dt.utcoffset()`.
    
-   Если вы просто хотите прикрепить объект часового пояса `tz` к `datetime.datetime()` без настройки даты и времени, используйте [`dt.replace(tzinfo=tz)`](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.replace).
    
-   Если вы просто хотите удалить объект часового пояса из "осведомленного" `datetime.datetime()` без преобразования даты и времени, используйте [`dt.replace(tzinfo=None)`](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.replace).
    

Обратите внимание, что метод `tzinfo.fromutc()` по умолчанию может быть переопределен в подклассе `tzinfo`, чтобы повлиять на результат, возвращаемый методом [`dt.astimezone()`](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.astimezone). действует так, что бы игнорировать ошибки `datetime.astimezone()`:

def astimezone(self, tz):
    if self.tzinfo is tz:
        return self
    # Конвертируйте self в UTC и прикрепите
    # новый объект часового пояса
    utc = (self - self.utcoffset()).replace(tzinfo=tz)
    # Конвертировать из UTC в местное время tz.
    return tz.fromutc(utc)

#### _`dt.utcoffset()`_:

Если `tzinfo=None`, то метод `dt.utcoffset()` возвращает `None`, иначе возвращает `self.tzinfo.utcoffset(self)` или вызывает исключение, если последний не возвращает `None` или объект `timedelta` со значением менее одного дня.

>>> import datetime
>>> dt = datetime.datetime.now()
>>> print(dt.utcoffset())
# None
>>> new_dt = dt.astimezone()
>>> new_dt.utcoffset()
# datetime.timedelta(0, 10800)

#### _`dt.dst()`_:

Если `tzinfo=None`, то метод `dt.dst()` возвращает `None`, иначе возвращает `self.tzinfo.dst(self)` или вызывает исключение, если последний не возвращает `None` или объект `timedelta` со значением менее одного дня.

>>> import datetime
>>> dt = datetime.datetime.now()
>>> print(dt.dst())
# None
>>> new_dt = dt.astimezone()
>>> print(new_dt.dst())
# None

#### _`dt.tzname()`_:

Если `tzinfo=None`, то метод `dt.tzname()` возвращает `None`, иначе возвращает `self.tzinfo.tzname(self)` или вызывает исключение, если последний не возвращает `None` или или строковый объект.

>>> import datetime
>>> dt = datetime.datetime.now()
>>> print(dt.tzname())
# None
>>> new_dt = dt.astimezone()
>>> new_dt.tzname()
# 'MSK'

#### _`dt.timetuple()`_:

Метод `dt.timetuple()` возвращает [кортеж](https://docs-python.ru/tutorial/osnovnye-vstroennye-tipy-python/tip-dannyh-tuple-kortezh/ "Тип данных tuple, кортеж в Python.") структуры времени [`time.struct_time`](https://docs-python.ru/standart-library/modul-time-python/klass-struct-time-modulja-time/ "Класс struct_time модуля time в Python."), например такой же как возвращает [`time.localtime()`](https://docs-python.ru/standart-library/modul-time-python/funktsija-localtime-modulja-time/ "Функция localtime() модуля time в Python.").

Метод `dt.timetuple()` эквивалентен:

time.struct_time((dt.year, dt.month, dt.day,
                  dt.hour, dt.minute, dt.second,
                  dt.weekday(), yday, dst))

где `yday = d.toordinal() - date(d.year, 1, 1).toordinal() + 1` номер дня в текущем году, начиная с 1 для 1 января. Флаг `tm_isdst` кортежа структуры устанавливается в соответствии с методом `dt.dst()`:

-   `tm_isdst` имеет значение -1, то `dt.dst()` возвращает `None`;
-   `tm_isdst` имеет значение 1, то `dt.dst()` возвращает ненулевое значение;
-   `tm_isdst` имеет значение 0.

>>> import datetime
>>> dt = datetime.datetime.now()
>>> dt.timetuple()
# time.struct_time(tm_year=2020, tm_mon=5, tm_mday=6, \
#                  tm_hour=9, tm_min=56, tm_sec=14, \
#                  tm_wday=2, tm_yday=127, tm_isdst=-1)
dt.timetuple().tm_isdst
# -1

#### _`dt.utctimetuple()`_:

Если экземпляр `dt` - "наивен", то метод `dt.utctimetuple()` возвратит же самое, что и [`dt.timetuple()`](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.timetuple), за исключением того, что элемент структуры `tm_isdst` принудительно устанавливается в 0 независимо от того, что возвращает [`dt.dst()`](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.dst). DST никогда не действует в течение времени UTC.

Если `dt` - "осведомленный", то `dt` нормализуется к времени UTC, вычитая [`dt.utcoffset()`](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.utcoffset) и возвращается [кортеж `time.struct_time`](https://docs-python.ru/standart-library/modul-time-python/klass-struct-time-modulja-time/ "Класс struct_time модуля time в Python.") для нормализованного времени. Значение `tm_isdst=0`. Обратите внимание, что [ошибка `OverflowError`](https://docs-python.ru/tutorial/vstroennye-iskljuchenija-interpretator-python/vstroennye-iskljuchenija/ "Исключения наследуемые от Exception в Python.") может быть вызвана, если атрибут даты и времени `dt.year` равняется `MINYEAR` или `MAXYEAR`, а корректировки UTC превышают границу года.

**Предупреждение**. Поскольку "наивные" объекты [`datetime.datetime()`](https://docs-python.ru/standart-library/modul-datetime-python/klass-datetime-modulja-datetime/ "Класс datetime() модуля datetime в Python.") обрабатываются многими методами как локальное время, то предпочтительно использовать ["осведомленные" объекты](https://docs-python.ru/standart-library/modul-datetime-python/ "Модуль datetime в Python, работа с датой и временем.") `datetime.datetime()` для представления времени в UTC. В результате использование конструктора [`datetime.datetime.utcfromtimetuple()`](https://docs-python.ru/standart-library/modul-datetime-python/klass-datetime-modulja-datetime/ "Класс datetime() модуля datetime в Python.") может привести к ошибочным результатам. Если у вас есть "наивный" объект `datetime.datetime()` представляющий UTC, то используйте [`dt.replace(tzinfo=timezone.utc)`](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.replace), чтобы сообщить, в какой момент вы можете использовать [`dt.timetuple()`](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.timetuple).

>>> import datetime
>>> dt = datetime.datetime.now()
>>> dt.timetuple()
# time.struct_time(tm_year=2020, tm_mon=5, tm_mday=6, \
#                  tm_hour=9, tm_min=56, tm_sec=14, \
#                  tm_wday=2, tm_yday=127, tm_isdst=0)
>>> dt.timetuple().tm_isdst
# 0

#### _`dt.toordinal()`_:

Метод `dt.toordinal()` возвращает пролептический григорианский порядковый номер даты. Так же, как `self.date().toordinal().`

>>> import datetime
>>> dt = datetime.datetime.now()
>>> dt.toordinal()
# 737551

#### _`dt.timestamp()`_:

Метод `dt.timestamp()` возвращает метку времени POSIX, соответствующую экземпляру `datetime.datetime()`. Возвращаемое значение - это [число с плавающей точкой](https://docs-python.ru/tutorial/osnovnye-vstroennye-tipy-python/tip-dannyh-float-veschestvennye-chisla/ "Тип данных float, вещественные числа в Python."), аналогичное тому, которое возвращает [`time.time()`](https://docs-python.ru/standart-library/modul-time-python/funktsija-time-modulja-time/ "Функция time() модуля time в Python.").

>>> import datetime
>>> dt = datetime.datetime.now()
>>> dt.timestamp()
1588748174.920298

Предполагается, что "наивные" экземпляры `datetime.datetime()` представляют местное время, и для выполнения преобразования используется метод платформы C `mktime()`. Поскольку `datetime.datetime()` поддерживает более широкий диапазон значений, чем `mktime()` на многих платформах, этот метод может вызвать [исключение `OverflowError`](https://docs-python.ru/tutorial/vstroennye-iskljuchenija-interpretator-python/vstroennye-iskljuchenija/ "Исключения наследуемые от Exception в Python.") для времен, которые уже прошли или будут в будущем.

Для "осведомленных" экземпляров `datetime.datetime()` возвращаемое значение вычисляется как:

>>> import datetime
>>> dt = datetime.datetime.now()
(dt - datetime.datetime(1970, 1, 1, tzinfo=timezone.utc)).total_seconds()

**Примечание**. Нет способа получить метку времени POSIX непосредственно из простого экземпляра `datetime.datetime()`, представляющего время UTC. Если ваше приложение использует это соглашение и системный часовой пояс не установлен на UTC, вы можете получитьвременную метку POSIX, указав `tzinfo=timezone.utc`:

>>> import datetime
>>> dt = datetime.datetime.now()
>>> timestamp = dt.replace(tzinfo=timezone.utc).timestamp()
# или путем вычисления метки времени напрямую:
>>> timestamp = (dt - datetime.datetime(1970, 1, 1)) / timedelta(seconds=1)

#### _`dt.weekday()`_:

Метод `dt.weekday()` возвращает день недели в виде [целого числа](https://docs-python.ru/tutorial/osnovnye-vstroennye-tipy-python/tip-dannyh-int-tselye-chisla/ "Тип данных int, целые числа в Python."), где понедельник = 0, а воскресенье = 6. То же, что `self.date().weekday()`.

Смотрите также метод [`dt.isoweekday()`](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.isoweekday).

>>> import datetime
>>> dt = datetime.datetime.now()
>>> dt.weekday()
2

#### _`dt.isoweekday()`_:

Метод `dt.isoweekday()` возвращает день недели в виде [целого числа](https://docs-python.ru/tutorial/osnovnye-vstroennye-tipy-python/tip-dannyh-int-tselye-chisla/ "Тип данных int, целые числа в Python."), где понедельник = 1, а воскресенье = 6. То же, что `self.date().isoweekday()`.

Смотрите также методы [`dt.weekday()`](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.weekday) и [`dt.isocalendar()`](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.isocalendar).

>>> import datetime
>>> dt = datetime.datetime.now()
>>> dt.isoweekday()
# 3

#### _`dt.isocalendar()`_:

Метод `dt.isocalendar()` возвращает [именованный кортеж](https://docs-python.ru/standart-library/modul-collections-python/klass-namedtuple-modulja-collections/ "Класс namedtuple() модуля collections в Python.") с тремя компонентами: год `year`, неделя `week` и день недели `weekday`. Так же, как `self.date().isocalendar()`.

>>> import datetime
>>> dt = datetime.datetime.now()
>>> dt.isocalendar()
# datetime.IsoCalendarDate(year=2020, week=19, weekday=3)

Изменено в Python 3.9: результат изменился с простого кортежа на именованный кортеж.

#### _`dt.isoformat(sep='T', timespec='auto')`_:

Метод `dt.isoformat()` возвращает [строку](https://docs-python.ru/tutorial/osnovnye-vstroennye-tipy-python/tip-dannyh-str-tekstovye-stroki/ "Тип данных str в Python, текстовые строки."), представляющую дату и время в формате ISO 8601:

-   YYYY-MM-DDTHH:MM:SS.ffffff, если микросекунда не равна 0
-   YYYY-MM-DDTHH:MM:SS, если микросекунда равна 0

Если [`dt.utcoffset()`](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.utcoffset) не возвращает `None`, добавляется строка, дающая смещение UTC:

-   YYYY-MM-DDTHH:MM:SS.ffffff+HH:MM[:SS[.ffffff]], если микросекунда не равна 0
-   YYYY-MM-DDTHH:MM:SS+HH:MM[:SS[.ffffff]], если микросекунда равна 0

Examples:

>>> import datetime
>>> dt = datetime.datetime.now()
>>> dt.isoformat()
# '2020-05-06T09:56:14.920298'
>>> tz = datetime.timezone.utc
>>> dt_utc = datetime.datetime.now(tz=tz)
>>> dt_utc.isoformat()
# '2020-05-06T06:56:14.920298+00:00'
>>> dt_local = dt.astimezone()
>>> dt_local.isoformat()
'2020-05-06T09:56:14.920298+03:00'

Необязательный аргумент `sep` - по умолчанию 'T', представляет собой односимвольный разделитель, помещенный между датой и временем.

import datetime

class TZ(datetime.tzinfo):
    """Часовой пояс с произвольным постоянным смещением -06: 39."""
    def utcoffset(self, dt):
        return datetime.timedelta(hours=-6, minutes=-39)

>>> datetime.datetime(2022, 12, 25, tzinfo=TZ()).isoformat(' ')
# '2022-12-25 00:00:00-06:39'
>>> datetime.datetime(2022, 11, 27, microsecond=100, tzinfo=TZ()).isoformat()
# '2022-11-27T00:00:00.000100-06:39'

Необязательный аргумент `timespec` указывает количество дополнительных компонентов времени для включения, по умолчанию "auto".

Это может быть одно из следующих:

-   `'auto'`: то же, что и `'seconds'`, если `dt.microseconds` равна 0, в противном случае как `'milliseconds'`.
-   `'hours'`: включает час в двузначном формате `HH`.
-   `'minutes'`: включает час и минуты в формате `HH:MM`.
-   `'seconds'`: включает час , минуты и секунды в формате `HH:MM:SS`.
-   `'milliseconds'`: включает полный вариант вывода, но усекает вторую дробную часть до миллисекунд - `HH:MM:SS.sss`.
-   `'microseconds'`: включает полный вариант вывода - `HH:MM:SS.ffffff`.

**Примечание**. Компоненты исключенного времени будут отброшены, а не округлены.

Будет вызвано [исключение `ValueError`](https://docs-python.ru/tutorial/vstroennye-iskljuchenija-interpretator-python/vstroennye-iskljuchenija/ "Исключения наследуемые от Exception в Python."), если аргумент `timespec` будет недопустимым.

>>> import datetime
>>> datetime.datetime.now().isoformat(timespec='minutes')   
# '2022-12-25T00:00'
>>> dt = datetime.datetime(2023, 1, 1, 12, 30, 59, 0)
>>> dt.isoformat(timespec='microseconds')
# '2023-01-01T12:30:59.000000'

#### _`dt.__str__()`_:

Для экземпляра `dt` справедливо утверждение: [`str(dt)`](https://docs-python.ru/tutorial/vstroennye-funktsii-interpretatora-python/klass-str/ "Класс str() в Python, преобразует объект в строку.") эквивалентно вызову [`dt.isoformat(sep=' ')`](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.isoformat).

>>> import datetime
>>> dt = datetime.datetime.now()
>>> dt.__str__()
# '2021-05-06 09:56:14.920298'
>>> str(dt)
# '2021-05-06 09:56:14.920298'

#### _`dt.ctime()`_:

Метод `dt.ctime()` возвращает [строку](https://docs-python.ru/tutorial/osnovnye-vstroennye-tipy-python/tip-dannyh-str-tekstovye-stroki/ "Тип данных str в Python, текстовые строки."), представляющую дату и время:

>>> import datetime
>>> dt = datetime.datetime.now()
>>> dt.ctime()
# 'Wed May  6 09:56:14 2021'

>>> import time
>>> time.ctime(time.mktime(dt.timetuple()))
# 'Wed May  6 09:56:14 2021'

Выходная строка не будет включать информацию о часовом поясе, независимо от того, является ли ввод ["осведомленным" или "наивным"](https://docs-python.ru/standart-library/modul-datetime-python/ "Модуль datetime в Python, работа с датой и временем.").

Вызов метода [`dt.ctime()`](https://docs-python.ru/standart-library/modul-datetime-python/metody-ekzempljara-ditetime-datetime/#dt.ctime) эквивалентен:

>>> import datetime, time
>>> dt = datetime.datetime.now()
>>> time.ctime(time.mktime(dt.timetuple()))
'Wed May  6 09:56:14 2021'

