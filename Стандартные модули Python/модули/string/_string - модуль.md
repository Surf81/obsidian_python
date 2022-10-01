# Модуль `string`
#string #строки
***
## Константы модуля `string`
***
Константы, определенные в этом модуле:

- `string.ascii_letters` - Объединение констант `ascii_lowercase` и `ascii_uppercase` описано ниже. Значение не зависит от языкового стандарта.
- `string.ascii_lowercase` - Строчные буквы `'abcdefghijklmnopqrstuvwxyz'`. Значение не зависит от локали и не изменится.
- `string.ascii_uppercase` - Заглавные буквы `'ABCDEFGHIJKLMNOPQRSTUVWXYZ'`. Значение не зависит от локали и не изменится.
- `string.digits` - Строка `'0123456789'`.
- `string.hexdigits` - Строка `'0123456789abcdefABCDEF'`.
- `string.octdigits` - Строка `'01234567'`.
- `string.punctuation` - Строка символов ASCII, которые считаются символами пунктуации в локали `C`: ``!"#$%&'()*+,-./:;<=>?@[\]^_`{|}~``.
- `string.printable` - Строка символов ASCII, которые считаются печатаемыми. Комбинация `digits`, `ascii_letters`, `punctuation` и `whitespace`.
- `string.whitespace` - Строка, содержащая все символы ASCII, считающиеся пробелами. Включает в себя пространство символов, табуляцию, перевод строки, возврат, перевод страницы и вертикальную табуляцию.
- 