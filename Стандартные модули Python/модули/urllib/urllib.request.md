# Модуль `urllib.request`
#urllib #url
***
## Отправка HTTP POST и GET запросов. Получение данных из URL-адресов.

## Получение данных с сайта по URL-адресу.

Самый простой способ использовать модуль `urllib.request` следующий:

```python
import urllib.request
with urllib.request.urlopen('http://python.org/') as resp:
   html = resp.read()
```

