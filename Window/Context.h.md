# Context.h - описание контекста окна

```#include <SFML/Window/Window/Context.h>```
<hr/>


```c
#ifndef SFML_CONTEXT_H
#define SFML_CONTEXT_H

////////////////////////////////////////////////////////////
// Headers
////////////////////////////////////////////////////////////
#include <SFML/Window/Export.h>
#include <SFML/Window/Types.h>
#include <SFML/Window/Window.h>
```
<hr/>

## sfContext_create - создает контекст

Аргументы:

- ``void`` - отсутствуют

**Возвращаемое значение:** ``sfContext*`` - ссылка на контекст окна.

```c
CSFML_WINDOW_API sfContext* sfContext_create(void);
```
<hr/>

## sfContext_destroy - удаляет контекст

Аргументы:

- ``sfContext* context`` - ссылка на контекст окна

**Возвращаемое значение:** ``void``.

```c
CSFML_WINDOW_API void sfContext_destroy(sfContext* context);
```
<hr/>

## sfContext_setActive - активироват/деактивировать контекст

Аргументы:

- ``sfContext* context`` - ссылка на контекст окна
- ``sfBool active`` - sfTrue активировать или sfFalse деактивировать

**Возвращаемое значение:** ``sfBool`` - результат операции (sfTrue удачно; sfFalse не удачно).

```c
CSFML_WINDOW_API sfBool sfContext_setActive(sfContext* context, sfBool active);
```
<hr/>

## sfContext_getSettings - получить настройки контекста

Реальные настройки контекста могут отличаться от переданных (зависит от поддержки контекста видеодрайвером). 
Данная функция возвращает реальные настройки контекста окна.

(см. Window/Window.h)

Аргументы:

- ``sfContext* context`` - ссылка на контекст окна

**Возвращаемое значение:** ``sfContextSettings`` - настройки контекста.

```c
CSFML_WINDOW_API sfContextSettings sfContext_getSettings(const sfContext* context);
```
<hr/>

## sfContext_getActiveContextId - получить идентификатор текущего активного контекста

Используется для идентификации контекстов при управлении закрытыми ресурсами OpenGL.

Аргументы:

- ``void`` - отсутствуют

**Возвращаемое значение:** ``sfUint64`` - идентификатор контекста.

```c
CSFML_WINDOW_API sfUint64 sfContext_getActiveContextId();
```
<hr/>

```c
#endif // SFML_CONTEXT_H
```
<hr/>



