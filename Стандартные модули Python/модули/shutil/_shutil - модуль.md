# Модуль `shutil`
#shutil #файлы 
***
## Копирование, удаление и архивирования файлов и директорий.

|метод|описание|
|---|---|
|**[`copyfile()`](#`copyfile()`)**|Функция `copyfile()` модуля `shutil` копирует содержимое файла, без метаданных|



Модуль `shutil` предлагает ряд высокоуровневых операций над файлами и коллекциями файлов. В частности, предусмотрены функции, которые поддерживают **копирование и удаление файлов**. Для операций над отдельными файлами, смотрите [модуль `os`](https://docs-python.ru/standart-library/modul-os-python/ "Модуль os в Python, доступ к функциям ОС.").

> **Предупреждение**.  
> Даже функции копирования файлов более высокого уровня `shutil.copy()`, `shutil.copy2()` не могут копировать все метаданные файла.

-   На платформах POSIX это означает, что владелец файла и группа будут потеряны, а также `ACL`.
-   В Mac OS ветвь ресурса и другие метаданные не используются. Это означает, что ресурсы будут потеряны, а тип файла и коды создателей будут неправильными.
-   В Windows владельцы файлов, списки ACL и альтернативные потоки данных не копируются.

Начиная с Python-3.8 все функции, включающие в себя функцию копирования файлов `shutil.copyfile()`, `shutil.copy()`, `shutil.copy2()`, `shutil.copytree()` и `shutil.move()`, могут использовать системные вызовы `fast-copy` для конкретной платформы, чтобы копировать файл более Эффективно. "Быстрое копирование" означает, что операция копирования происходит внутри ядра, избегая использования буферов пространства пользователя в Python.

Если операция быстрого копирования завершится неудачно и данные в файл назначения не будут записаны, модуль `shutil` автоматически откажется от использования менее эффективной функции `copyfileobj()`.


## `copyfile()`
Копирует содержимое источника в место назначения и вызывает [исключение `IOError`](https://docs-python.ru/tutorial/vstroennye-iskljuchenija-interpretator-python/oshibki-operatsionnoj-sistemy-oserror/ "Исключения операционной системы: OSError в Python."), если у него нет разрешения на запись в файл назначения.
Функция `copyfile()` модуля `shutil` копирует содержимое файла, без метаданных, с именем `src` в файл с именем `dst` наиболее эффективным способом. В случае успеха возвращает имя скопированного `dst`.
```python
shutil.copyfile(src, dst, *, follow_symlinks=True)
```
#### Параметры:
-   `src` - исходное место/путь копируемого файла ,
-   `dst` - место/путь назначения нового файла,
-   `follow_symlinks=True` - что делать с символическими ссылками.

#### Возвращаемое значение:
-   [`str`](https://docs-python.ru/tutorial/osnovnye-vstroennye-tipy-python/tip-dannyh-str-tekstovye-stroki/ "Текстовые строки str в Python.") имя скопированного `dst`.

```python
import shutil, os
from glob import glob
# создадим временную директорию 
os.mkdir('example')
# создадим тестовый файл
open('example/test_file.txt', 'w').close()
# копирование
shutil.copyfile('example/test_file.txt', 'example/test_file.txt.copy')
# 'example/test-file.txt.copy'

# смотрим результат
pprint.pprint(glob('example/*'))
# ['example/test_file.txt.copy', 'example/test_file.txt']

# удаляем
shutil.rmtree('example')
```


## `copy()`
 Интерпретирует имя выходного файла как инструмент командной строки Unix `cp`. Если путь назначения указан как каталог, а не файл, то в каталоге создается новый файл с использованием его базового имени.

```python
import shutil, os
from glob import glob
# создадим тестовый файл
open('shutil_copy.txt', 'w').close()
# создадим временную директорию 
os.mkdir('example')
glob('example/*')
# []

# копируем
shutil.copy('shutil_copy.txt', 'example')
# 'example/shutil_copy.txt'

# смотрим результат
glob('example/*')
# ['example/shutil_copy.txt']

# удаляем
shutil.rmtree('example')
```

## `copytree()`
 Рекурсивно копирует весь каталог.

```python
# для того что бы протестировать функцию copytree()
# создадим иерархию каталогов
import pathlib, itertools, glob, shutil
path = 'test/'
tmp = {'script':'.py', 'text':'.txt'}
for d, ext in tmp.items():
    comb = itertools.combinations([d, 1, 0], r=2)
    for a, b in comb:
        name = f'{a}{b}{ext}'
        pathlib.Path(path, d).mkdir(parents=True, exist_ok=True)
        pathlib.Path(path, d, name).touch(exist_ok=True)

f = glob.glob('test/**/*', recursive=True)
print(f)
# ['test/text', 'test/script', 'test/text/10.txt', 
# 'test/text/text1.txt', 'test/text/text0.txt',
# 'test/script/10.py', 'test/script/script0.py', 
# 'test/script/script1.py']

# копируем
shutil.copytree('test', 'test_cp')
# смотрим результат
f_cp = glob.glob('test_cp/**/*', recursive=True)
print(f_cp)

# ['test/text', 'test/script', 'test/text/10.txt', 
# 'test/text/text1.txt', 'test/text/text0.txt',
# 'test/script/10.py', 'test/script/script0.py', 
# 'test/script/script1.py']

# удаляем
shutil.rmtree('test_cp')
shutil.rmtree('test')
```

Пример, который использует помощник [`shutil.ignore_patterns()`](https://docs-python.ru/standart-library/modul-shutil-python/funktsija-ignore-patterns-modulja-shutil/ "Функция ignore_patterns() модуля shutil в Python."). Здесь копируется все, кроме файлов `.pyc` и файлов или каталогов, чье имя начинается с `tmp`.

```python
from shutil import copytree, ignore_patterns
copytree(source, destination, ignore=ignore_patterns('*.pyc', 'tmp*'))
```

Другой пример, который использует аргумент `ignore` для добавления вызова логирования копирования файлов:

```python
from shutil import copytree
import logging

def _logpath(path, names):
    logging.info('Working in %s', path)
    return []   # nothing will be ignored

copytree(source, destination, ignore=_logpath)
```

## `rmtree()`
#### Рекурсивное удаление каталога


В этом примере показано, как удалить дерево каталогов в Windows, где для некоторых файлов установлен бит только для чтения. Он использует обратный вызов `onerror`, чтобы очистить бит `readonly` и повторить попытку удаления.

```python
import os, stat
import shutil

def remove_readonly(func, path, _):
    "Clear the readonly bit and reattempt the removal"
    os.chmod(path, stat.S_IWRITE)
    func(path)

shutil.rmtree(directory, onerror=remove_readonly)
```

В функции `shutil.rmtree()`, так же можно использовать помощник `shutil.ignore_patterns()` для **выборочного рекурсивного удаления файлов** как это делается в примере выборочного рекурсивного копирования файлов.