# Color.h - описание цвета


```#include <SFML/Graphics/Color.h>```
<hr/>

```c
#ifndef SFML_COLOR_H
#define SFML_COLOR_H

////////////////////////////////////////////////////////////
// Headers
////////////////////////////////////////////////////////////
#include <SFML/Graphics/Export.h>
```
<hr/>

## sfColor - описание цвета в формате RGBA

Компонент цвета в диапазоне [0 .. 255]

```c
typedef struct
{
    sfUint8 r;
    sfUint8 g;
    sfUint8 b;
    sfUint8 a;
} sfColor;
```
<hr/>

## Предопределенные цвета

```c
CSFML_GRAPHICS_API sfColor sfBlack;       ///< Черный
CSFML_GRAPHICS_API sfColor sfWhite;       ///< Белый
CSFML_GRAPHICS_API sfColor sfRed;         ///< Красный
CSFML_GRAPHICS_API sfColor sfGreen;       ///< Зеленый
CSFML_GRAPHICS_API sfColor sfBlue;        ///< Синий
CSFML_GRAPHICS_API sfColor sfYellow;      ///< Желтый
CSFML_GRAPHICS_API sfColor sfMagenta;     ///< Пурпурный
CSFML_GRAPHICS_API sfColor sfCyan;        ///< Голубой
CSFML_GRAPHICS_API sfColor sfTransparent; ///< Черный с каналом прозрачности 
```
<hr/>

## sfColor_fromRGB - создает цвет по 3м компонентам (RGB)

Аргументы:

- ``sfUint8 red`` -   R красный  (0 .. 255)
- ``sfUint8 green`` - G зеленый  (0 .. 255)
- ``sfUint8 blue`` -  B синий    (0 .. 255)

**Возвращаемое значение:** ``sfColor`` - структура цвета.

```c
CSFML_GRAPHICS_API sfColor sfColor_fromRGB(sfUint8 red, sfUint8 green, sfUint8 blue);
```
<hr/>

## sfColor_fromRGBA - создает цвет по 4м компонентам (RGBA)

Аргументы:

- ``sfUint8 red`` -   R красный      (0 .. 255)
- ``sfUint8 green`` - G зеленый      (0 .. 255)
- ``sfUint8 blue`` -  B синий        (0 .. 255)
- ``sfUint8 alpha`` - A прозрачность (0 .. 255)

**Возвращаемое значение:** ``sfColor`` - структура цвета.

```c
CSFML_GRAPHICS_API sfColor sfColor_fromRGBA(sfUint8 red, sfUint8 green, sfUint8 blue, sfUint8 alpha);
```
<hr/>

## sfColor_fromInteger - создает цвет по коду

Коды цвета в формате RGBA (32 бита) по 8 бит на цвет.

Например: белый цвет <= 0xFFFFFFFF

Аргументы:

- ``sfUint32 color`` - цвет в коде

**Возвращаемое значение:** ``sfColor`` - структура цвета.

```c
CSFML_GRAPHICS_API sfColor sfColor_fromInteger(sfUint32 color);
```
<hr/>

## sfColor_toInteger - получить код по цвету

Получить код цветового представления

Например: белый цвет => 0xFFFFFFFF

Аргументы:

- ``sfColor color`` - цветовое представление

**Возвращаемое значение:** ``sfUint32`` - код цвета.

```c
CSFML_GRAPHICS_API sfUint32 sfColor_toInteger(sfColor color);
```
<hr/>

## sfColor_add - сложение 2х цветов (смещение)

Аргументы:

- ``sfColor color1`` - цветовое представление 1
- ``sfColor color2`` - цветовое представление 2

**Возвращаемое значение:** ``sfColor`` - результирующий цвет.

```c
CSFML_GRAPHICS_API sfColor sfColor_add(sfColor color1, sfColor color2);
```
<hr/>

## sfColor_subtract - разница 2х цветов (остаточный цвет)

Аргументы:

- ``sfColor color1`` - цветовое представление 1
- ``sfColor color2`` - цветовое представление 2

**Возвращаемое значение:** ``sfColor`` - результирующий цвет.

```c
CSFML_GRAPHICS_API sfColor sfColor_subtract(sfColor color1, sfColor color2);
```
<hr/>

## sfColor_modulate - перемножение 2х цветов (модуляция цвета)

Аргументы:

- ``sfColor color1`` - цветовое представление 1
- ``sfColor color2`` - цветовое представление 2

**Возвращаемое значение:** ``sfColor`` - результирующий цвет.

```c
CSFML_GRAPHICS_API sfColor sfColor_modulate(sfColor color1, sfColor color2);
```
<hr/>

```c
#endif // SFML_COLOR_H
```
<hr/>


