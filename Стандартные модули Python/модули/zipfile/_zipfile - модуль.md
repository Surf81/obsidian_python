# Модуль `zipfile`
#zipfile #файлы 
***
## Классы и методы модуля `zipfile`
***
- **[ZipFile(file, mode)](#ZipFile%20file%20str%20mode%20str)**() - объект для работы с файлами `zip`

### `ZipFile(file: str, mode: str)`:

#### Не обязательные параметры:
- `mode`, который задает режим работы (по аналогии с обычными файлами) (по умолчанию равен `r`):
	-   `r` — файл будет открыт для чтения
	-   `w` — если файл существует, то он будет уничтожен и вместо него будет создан новый файл
	-   `a` — существующий файл будет открыт в режиме добавления в конец
-   `compression` определяет метод сжатия, который должен использоваться при записи в архив. Он принимает одно из значений: `ZIP_STORED, ZIP_DEFLATED, ZIP_BZIP2, ZIP_LZMA`. По умолчанию используется значение `compression=ZIP_STORED`
-   `allowZip64` позволяет разрешить использование расширений `zip64`, которые дают возможность создавать архивы размером больше 4 гигабайт. По умолчанию равен `allowZip64=False`
```python
from zipfile import ZipFile 
with ZipFile('test.zip') as zip_file: 
	zip_file.printdir()
```

#### Методы:
- **[extract(file, path)](#extract%20file%20path)** - извлечение файла в каталог
- **[extractall(path)](#extractall%20path)** - извлечение всех файлов
- **[getinfo()](#getinfo)** - информация о конкретнойм файле из архива
- **[infolist()](#infolist)** - информация о файлах из архива, список элементов `ZipInfo`
- **[ZipInfo.is_dir()](#is_dir)** - определяет содержимое папка или файл
- **[is_zipfile()](#is_zipfile)** - проверяет файл на соответствие формату `zip`
- **[namelist()](#namelist)** - возвращает пути ко всем файлам и папкам архива
- **[open()](#open)** - открывает файл для работы с ним
- **[printdir()](#printdir)** - список содержимого архива

#### `extract(file, path)`:
Извлечение файла `file` из архива в каталог `path`

```python
from zipfile import ZipFile 
with ZipFile('test.zip') as zip_file: 
	zip_file.extract('test/Картинки/avatar.png') 
	zip_file.extract('test/Программы/image_util.py') 
	zip_file.extract('lse.jpeg')
```

#### `extractall(path)`:
Извлечение всех файлов в каталог `path`. Если не указан, то в текущий
##### Не обязательные параметры:
- `members` - кортеж или список фалов для извлечения. По утолчанию `None`

#### `getinfo()`:
```python
from zipfile import ZipFile 
with ZipFile('test.zip') as zip_file: 
	info = zip_file.namelist() # получаем названия всех файлов архива 
	last_file = zip_file.getinfo(info[-4]) # получаем информацию об отдельном файле 
	print(last_file.file_size) 
	print(last_file.compress_size) 
	print(last_file.filename) 
	print(last_file.date_time)
```

#### `infolist()`:
Метод `infolist()` позволяет получить информацию о файлах из архива в виде списка `list` специальных объектов (тип `ZipInfo`), которые содержат дополнительную информацию о каждом файле:
-   `file_size` - размер до сжатия в байтах
-   `compress_size` - размер после сжатия в байтах
-   `filename` - имя файла
-   `date_time` - дата изменения файла в виде кортежа (год, месяц, день, час, минута, секунда)
-   ...

#### `is_dir()`:
Определяет, является ли содержимое объекта `ZipInfo` папкой или файлом

#### `is_zipfile()`:
принимает на вход путь к файлу (или сам файловый объект) и возвращает значение `True`, если указанный файл является `zip` архивом, или `False` в противном случае

#### `namelist()`:
Возвращает пути ко всем папкам и файлам архива

#### `open()`:
Открывает файл для работы с ним. Файл открывается в виде бинарной строки. Для перевода в текстовый формат необходимо использовать метод `decode()` типа `bytes`
```python
from zipfile import ZipFile 
with ZipFile('test.zip') as zip_file: 
	with zip_file.open('test/Разные файлы/astros.json') as file: 
		print(file.read())
```

```python
from zipfile import ZipFile 
with ZipFile('test.zip') as zip_file: 
	with zip_file.open('test/Разные файлы/astros.json') as file: 
		print(file.read().decode('utf-8'))
```

#### `printdir()`:
Список содержимого архива

#### `write()`:
Запись файла в архив
```python
from zipfile import ZipFile 
with ZipFile('archive.zip', mode='a') as zip_file: #mode='a' для записи в существующий архив
	zip_file.write('program.py', 'test/new_program.py') # первый аргумент - это имя файла 
	zip_file.write('lse.jpeg', 'lse1.jpeg') # второй аргумент - это имя файла в архиве 
	print(zip_file.namelist())
```