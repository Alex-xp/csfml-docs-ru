# Clipboard.h - работа с буфером обмена

```#include <SFML/Window/Clipboard.h>```
<hr/>


```c
#ifndef SFML_CLIPBOARD_H
#define SFML_CLIPBOARD_H

////////////////////////////////////////////////////////////
// Headers
////////////////////////////////////////////////////////////
#include <SFML/Window/Export.h>
#include <SFML/Window/Types.h>
```
<hr/>

## sfClipboard_getString - получить строку из буфера обмена

Эта функция возвращает содержимое буфера обмена в виде строки. Если буфер обмена не содержит строки, вернет пустую строку.

Работает со строками ANSII и UTF-8.

**Возвращаемое значение:** ``const char*`` - строка (или NULL)

```c
CSFML_WINDOW_API const char* sfClipboard_getString();
```
<hr/>

## sfClipboard_getUnicodeString - получить строку из буфера обмена в UTF-32

Эта функция возвращает содержимое буфера обмена в виде строки. Если буфер обмена не содержит строки, вернет пустую строку.

Работает со строками ENICODE и UTF-32.

**Возвращаемое значение:** ``const sfUint32*`` - строка (или NULL)

```c
CSFML_WINDOW_API const sfUint32* sfClipboard_getUnicodeString();
```
<hr/>

## sfClipboard_setString - отправить строку в буфер обмена

Работает со строками ANSII и UTF-8.

Аргументы:

- ``const char* text`` - строка

**Возвращаемое значение:** ``void`` 

```c
CSFML_WINDOW_API void sfClipboard_setString(const char* text);
```
<hr/>

## sfClipboard_setUnicodeString - отправить строку в буфер обмена в UTF-32

Работает со строками ENICODE и UTF-32.

Аргументы:

- ``const sfUint32* text`` - строка

**Возвращаемое значение:** ``void``

```c
CSFML_WINDOW_API void sfClipboard_setUnicodeString(const sfUint32* text);
```
<hr/>


```c
#endif // SFML_CURSOR_H
```
<hr/>



