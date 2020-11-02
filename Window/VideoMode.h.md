# VideoMode.h - видеорежимы

```#include <SFML/Window/VideoMode.h>```
<hr/>

```c
#ifndef SFML_VIDEOMODE_H
#define SFML_VIDEOMODE_H

////////////////////////////////////////////////////////////
// Headers
////////////////////////////////////////////////////////////
#include <SFML/Window/Export.h>
#include <stddef.h>
```
<hr/>


## sfVideoMode - описание видеорежима

Структура описания видеорежима. Описывает поддерживаемый режим видеоустройством.

```c
typedef struct
{
    unsigned int width;        ///< Ширина в пикселах
    unsigned int height;       ///< Высота в пикселах
    unsigned int bitsPerPixel; ///< Глубина цветности в битах (8, 16, 24, 32)
} sfVideoMode;
```
<hr/>

## sfVideoMode_getDesktopMode - видеорежим дисплея

Получить видеорежим рабочего стола.

Аргументы:

- ``void`` - отсутствуют

**Возвращаемое значение:** ``sfVideoMode`` - структура видеорежима.

```c
CSFML_WINDOW_API sfVideoMode sfVideoMode_getDesktopMode(void);
```
<hr/>

## sfVideoMode_getFullscreenModes - список видеорежимов

Возвращает список видеорежимов, поддерживаемый драйвером видеоустройства. 
Данные видеорежимы могут использоваться для работы в полноэкранном режиме. 
Получаемый список будет содержать видеорежимы от лучшего к худшему.

Аргументы:

- ``size_t* count`` - количество видеорежимов, которое нужно получить.

**Возвращаемое значение:** ``sfVideoMode*`` - указатель на первый видеорежим в списке. Первый видеорежим всегда имеет самое высокое разрешение и глубину цвета.

```c
CSFML_WINDOW_API const sfVideoMode* sfVideoMode_getFullscreenModes(size_t* count);
```
<hr/>

## sfVideoMode_isValid - проверка видеорежима

Узнать, поддерживается ли видеорежим драйвером видеокарты.

Аргументы:

- ``sfVideoMode mode`` - структура описывающая проверяемый видеорежим.

**Возвращаемое значение:** ``sfBool`` - sfTrue - если режим поддерживается (sfFalse - не поддерживается).

```c
CSFML_WINDOW_API sfBool sfVideoMode_isValid(sfVideoMode mode);
```
<hr/>



```c
#endif // SFML_VIDEOMODE_H
```
