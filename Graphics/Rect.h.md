# Rect.h - прямоугольная область

```#include <SFML/Graphics/Rect.h>```
<hr/>

```c
#ifndef SFML_RECT_H
#define SFML_RECT_H

////////////////////////////////////////////////////////////
// Headers
////////////////////////////////////////////////////////////
#include <SFML/Graphics/Export.h>
```
<hr/>

## sfFloatRect - прямоугольная область, описаная числами с плавающей точкой

```c
typedef struct
{
    float left;   //< левая сторона (координата x)
    float top;    //< верхняя сторона (координата y)
    float width;  //< ширина
    float height; //< высота
} sfFloatRect;
```
<hr/>

## sfIntRect - прямоугольная область, описаная целыми числами

```c
typedef struct
{
    int left;   //< левая сторона (координата x)
    int top;    //< верхняя сторона (координата y)
    int width;  //< ширина
    int height; //< высота
} sfIntRect;
```
<hr/>

## Проверка вхождения точки в область

```sfFloatRect_contains``` - проверка области sfFloatRect

```sfIntRect_contains``` - проверка области sfIntRect

Аргументы:

- ``rect`` - область
- ``x`` - координата точки x
- ``y`` -  координата точки y

**Возвращаемое значение:** ``sfBool`` - результат (sfTrue - входит; sfFalse - не входит).

```c
CSFML_GRAPHICS_API sfBool sfFloatRect_contains(const sfFloatRect* rect, float x, float y);
CSFML_GRAPHICS_API sfBool sfIntRect_contains(const sfIntRect* rect, int x, int y);
```
<hr/>

## Проверка пересечения областей

```sfFloatRect_intersects``` - проверка областей sfFloatRect

```sfIntRect_intersects``` - проверка областей sfIntRect

Аргументы:

- ``rect1`` - область 1
- ``rect2`` - область 2
- ``intersection`` -  заполнение перекрывающейся области (или NULL) - если указано, тогда сюда вернет область перекрытия

**Возвращаемое значение:** ``sfBool`` - результат (sfTrue - пересечение есть; sfFalse - пересечения нет).


```c
CSFML_GRAPHICS_API sfBool sfFloatRect_intersects(const sfFloatRect* rect1, const sfFloatRect* rect2, sfFloatRect* intersection);
CSFML_GRAPHICS_API sfBool sfIntRect_intersects(const sfIntRect* rect1, const sfIntRect* rect2, sfIntRect* intersection);
```
<hr/>

```c
#endif // SFML_RECT_H
```
<hr/>
