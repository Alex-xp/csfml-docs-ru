# Cursor.h - курсоры мышки

```#include <SFML/Window/Cursor.h>```
<hr/>

```c
#ifndef SFML_CURSOR_H
#define SFML_CURSOR_H

////////////////////////////////////////////////////////////
// Headers
////////////////////////////////////////////////////////////
#include <SFML/System/Vector2.h>
#include <SFML/Window/Export.h>
#include <SFML/Window/Types.h>
```
<hr/>

## sfCursorType - перечисление системных курсоров

Курсор мышки определяется нативно для каждой операционной системы. 
В таблице ниже - приведен список поддерживаемых курсоров:

|  Type                           | Linux | Mac OS X | Windows  |
|---------------------------------|-------|----------|----------|
|  sfCursorArrow                  |  yes  |    yes   |   yes    |
|  sfCursorArrowWait              |  no   |    no    |   yes    |
|  sfCursorWait                   |  yes  |    no    |   yes    |
|  sfCursorText                   |  yes  |    yes   |   yes    |
|  sfCursorHand                   |  yes  |    yes   |   yes    |
|  sfCursorSizeHorizontal         |  yes  |    yes   |   yes    |
|  sfCursorSizeVertical           |  yes  |    yes   |   yes    |
|  sfCursorSizeTopLeftBottomRight |  no   |    no    |   yes    |
|  sfCursorSizeBottomLeftTopRight |  no   |    no    |   yes    |
|  sfCursorSizeAll                |  yes  |    no    |   yes    |
|  sfCursorCross                  |  yes  |    yes   |   yes    |
|  sfCursorHelp                   |  yes  |    no    |   yes    |
|  sfCursorNotAllowed             |  yes  |    yes   |   yes    |


```c
typedef enum
{
    sfCursorArrow,                  ///< Стрелка (по умолчанию)
    sfCursorArrowWait,              ///< Стрелка + часы (занятость)
    sfCursorWait,                   ///< Часы
    sfCursorText,                   ///< Курсор ввода текста (балка)
    sfCursorHand,                   ///< Указатель пальцем руки
    sfCursorSizeHorizontal,         ///< Двойная горизонтальная стрелка
    sfCursorSizeVertical,           ///< Двойная вертикальная стрелка
    sfCursorSizeTopLeftBottomRight, ///< Курсор изменения размеров по диагонали (верх-лево <-> низ-право)
    sfCursorSizeBottomLeftTopRight, ///< Курсор изменения размеров по диагонали (верх-право <-> низ-лево)
    sfCursorSizeAll,                ///< Курсор изменения размеров по диагонали (все направления)
    sfCursorCross,                  ///< Курсор-перекрестие
    sfCursorHelp,                   ///< Курсор помощи
    sfCursorNotAllowed              ///< Курсор - действие не доступно
} sfCursorType;
```
<hr/>

## sfCursor_createFromPixels - создать курсор из изображения

Изображение должно быть загружено в память. 
При этом в памяти должен получиться двумерный массив пикселей изображения.
Описание каждого пикселя должно иметь 32х битный формат RGBA (1 пиксель = 32*4 = 128 бит = 16 байт).

Если пиксели, ширина, либо высота равны нулю, тогда функция возвращает sFalse и текущий курсор остается неизменным.

Также можно указать расположение активной точки курсора. 
Активная точка - это координата пикселя в изображении курсора, которая будет указывать точное мето действия мышки под курсором.

ЗАМЕЧАНИЕ: В системах типа Unix (Linux и X11), курсор имеет монохромное растровое изображение, то есть изображение будет скорректировано по следующим правилам:
- пиксели с альфа-каналом равным 0 - являются прозрачными;
- если канал RGB близок к нулю - черными;
- белым в противном случае.

Аргументы:

- ``const sfUint8* pixels`` - массив пикселей изображения в памяти
- ``sfVector2u size`` - высота и ширина изображения (массива) в пикселях
- ``sfVector2u hotspot`` - активная точка

**Возвращаемое значение:** ``sfCursor*`` - ссылка на курсор (NULL при ошибке)


```c
CSFML_WINDOW_API sfCursor* sfCursor_createFromPixels(const sfUint8* pixels, sfVector2u size, sfVector2u hotspot);
```
<hr/>

## sfCursor_createFromSystem - создать нативный системный курсор

Аргументы:

- ``sfCursorType type`` - тип курсора из перечисления выше

**Возвращаемое значение:** ``sfCursor*`` - ссылка на курсор (NULL при ошибке)


```c
CSFML_WINDOW_API sfCursor* sfCursor_createFromSystem(sfCursorType type);
```
<hr/>

## sfCursor_destroy - удалить курсор

Аргументы:

- ``sfCursor* cursor`` - ссылка на курсор

**Возвращаемое значение:** ``void``

```c
CSFML_WINDOW_API void sfCursor_destroy(sfCursor* cursor);
```
<hr/>

```c
#endif // SFML_CURSOR_H
```
<hr/>





