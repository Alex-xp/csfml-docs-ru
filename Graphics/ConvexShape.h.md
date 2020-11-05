# ConvexShape.h - пользовательская геометрическая форма

```#include <SFML/Graphics/ConvexShape.h>```

Рисует форму с произвольным контуром, указываемым по точкам.

<hr/>

```c
#ifndef SFML_CONVEXSHAPE_H
#define SFML_CONVEXSHAPE_H

////////////////////////////////////////////////////////////
// Headers
////////////////////////////////////////////////////////////
#include <SFML/Graphics/Export.h>
#include <SFML/Graphics/Color.h>
#include <SFML/Graphics/Rect.h>
#include <SFML/Graphics/Transform.h>
#include <SFML/Graphics/Types.h>
#include <SFML/System/Vector2.h>
#include <stddef.h>

```
<hr/>

## sfConvexShape_create - создать форму

**Возвращаемое значение:** ``sfConvexShape*`` - указатель на фигуру (NULL - при неудаче)

```c
CSFML_GRAPHICS_API sfConvexShape* sfConvexShape_create(void);
```
<hr/>

## sfConvexShape_copy - полное копирование формы

Аргументы:

- ``const sfConvexShape* shape`` - копируемая форма

**Возвращаемое значение:** ``sfRectangleShape*`` - указатель на копию формы (NULL - при неудаче)

```c
CSFML_GRAPHICS_API sfConvexShape* sfConvexShape_copy(const sfConvexShape* shape);
```
<hr/>

## sfConvexShape_destroy - удалить форму

Аргументы:

- ``const sfConvexShape* shape`` - удаляемая форма

```c
CSFML_GRAPHICS_API void sfConvexShape_destroy(sfConvexShape* shape);
```
<hr/>

## sfConvexShape_setPosition - установить позицию

Аргументы:

- ``sfConvexShape* shape`` - форма
- ``sfVector2f position`` - новая позиция

```c
CSFML_GRAPHICS_API void sfConvexShape_setPosition(sfConvexShape* shape, sfVector2f position);
```
<hr/>

## sfConvexShape_setRotation - установить угол поворота

Полностью переписывает поворот объекта на указанный угол.

По умолчанию угол = 0

Аргументы:

- ``sfConvexShape* shape`` - форма
- ``float angle`` - угол в градусах

```c
CSFML_GRAPHICS_API void sfConvexShape_setRotation(sfConvexShape* shape, float angle);
```
<hr/>

## sfConvexShape_setScale - установить масштаб

Перезапишет текущий масштаб.

По умолчанию масштаб = (1, 1)

Аргументы:

- ``sfConvexShape* shape`` - форма
- ``sfVector2f scale`` - масштаб

```c
CSFML_GRAPHICS_API void sfConvexShape_setScale(sfConvexShape* shape, sfVector2f scale);
```
<hr/>

## sfConvexShape_setOrigin - установить относительную точку трансформации 

Исходная точка преобразований для объекта, определяет центральную точку трансформаций (перемещение, масштаб, поворот).
Координаты этой точки обычно устанавливаются относительно верхнего левого угла объекта и не учавствуют в преобразованиях.

Исходная точка преобразований по умолчанию = (0, 0).

Аргументы:

- ``sfConvexShape* shape`` - форма
- ``sfVector2f origin`` - точка преобразований

```c
CSFML_GRAPHICS_API void sfConvexShape_setOrigin(sfConvexShape* shape, sfVector2f origin);
```
<hr/>

## sfConvexShape_getPosition - получить позицию объекта

Аргументы:

- ``const sfConvexShape*`` - форма

**Возвращаемое значение:** ``sfVector2f`` - позиция

```c
CSFML_GRAPHICS_API sfVector2f sfConvexShape_getPosition(const sfConvexShape* shape);
```
<hr/>

## sfConvexShape_getRotation - получить угол поворота

Аргументы:

- ``const sfConvexShape* shape`` - форма

**Возвращаемое значение:** ``float`` - угол в градусах

```c
CSFML_GRAPHICS_API float sfConvexShape_getRotation(const sfConvexShape* shape);
```
<hr/>

## sfConvexShape_getScale - получить масштаб объекта

Аргументы:

- ``const sfConvexShape* shape`` - форма

**Возвращаемое значение:** ``sfVector2f`` - масштаб

```c
CSFML_GRAPHICS_API sfVector2f sfConvexShape_getScale(const sfConvexShape* shape);
```
<hr/>

## sfConvexShape_getOrigin - получить локальную точку трансформации

Локальная точка определяется относительно объекта (относительно левого верхнего угла области объекта).

Аргументы:

- ``const sfConvexShape* shape`` - форма

**Возвращаемое значение:** ``sfVector2f`` - точка трансформации

```c
CSFML_GRAPHICS_API sfVector2f sfConvexShape_getOrigin(const sfConvexShape* shape);
```
<hr/>

## sfConvexShape_move - перемещение объекта

Аргументы:

- ``sfConvexShape* shape`` - форма
- ``sfVector2f offset`` - смещение

```c
CSFML_GRAPHICS_API void sfConvexShape_move(sfConvexShape* shape, sfVector2f offset);
```
<hr/>

## sfConvexShape_rotate - повернуть объект

Аргументы:

- ``sfConvexShape* shape`` - форма
- ``float angle`` - угол поворота в градусах

```c
CSFML_GRAPHICS_API void sfConvexShape_rotate(sfConvexShape* shape, float angle);
```
<hr/>

## sfConvexShape_scale - изменить масштаб объекта

В отличие от sfShape_setScale, эта функция умножает текущий масштаб объекта, а не перезаписывает.

Аргументы:

- ``sfConvexShape* shape`` - форма
- ``sfVector2f factors`` - масштаб

```c
CSFML_GRAPHICS_API void sfConvexShape_scale(sfConvexShape* shape, sfVector2f factors);
```
<hr/>

## sfConvexShape_getTransform - получить матрицу преобразований объекта

Аргументы:

- ``const sfConvexShape* shape`` - форма

**Возвращаемое значение:** ``sfTransform`` - матрица преобразований 3x3

```c
CSFML_GRAPHICS_API sfTransform sfConvexShape_getTransform(const sfConvexShape* shape);
```
<hr/>

## sfConvexShape_getInverseTransform - получить обратную матрицу преобразований объекта

Аргументы:

- ``const sfConvexShape* shape`` - форма

**Возвращаемое значение:** ``sfTransform`` - матрица преобразований 3x3

```c
CSFML_GRAPHICS_API sfTransform sfConvexShape_getInverseTransform(const sfConvexShape* shape);
```
<hr/>

## sfConvexShape_setTexture  - установить исходную текстуру объекта

Объект работает с текстурой в памяти. Текстура представляет собой графический вид объекта. 
Переданная текстура в аргументе данной функции, должна существовать в памяти на протяжении работы объекта.
Если текстуру удалить до окончания работы объекта, может возникнуть ситуация обращения к пустому указателю.

Чтобы отключить текстуру, можно передать NULL.

Аргументы:

- ``sfConvexShape* shape`` - форма
- ``const sfTexture* texture`` - текстура (или NULL, чтобы отключить текстуру)
- ``sfBool resetRect`` - автоматически подгонять размер объекта под текстуру (sfTrue - заставит объект подогнать свои размеры под под размеры текстуры)

```c
CSFML_GRAPHICS_API void sfConvexShape_setTexture(sfConvexShape* shape, const sfTexture* texture, sfBool resetRect);
```
<hr/>

## sfConvexShape_setTextureRect - отображение части текстуры

При помощи этой функции можно отобразить не всю текстуру целиком, а её часть, описаную прямоугольником.

По умолчанию отображается вся текстура.

Аргументы:

- ``sfConvexShape* shape`` - форма
- ``sfIntRect rect`` - область отображения

```c
CSFML_GRAPHICS_API void sfConvexShape_setTextureRect(sfConvexShape* shape, sfIntRect rect);
```
<hr/>

## sfConvexShape_setFillColor - цвет заливки

Цвет заливки умножается на цвет текстуры. 

Используя sfTransparent - можно создать прозрачную заливку, оставив только контур.

По умолчанию цвет заливки белый.

Аргументы:

- ``sfConvexShape* shape`` - форма
- ``sfColor color`` - цвет заливки

```c
CSFML_GRAPHICS_API void sfConvexShape_setFillColor(sfConvexShape* shape, sfColor color);
```
<hr/>

## sfConvexShape_setOutlineColor - цвет контура

Используя sfTransparent - можно создать прозрачный контур.

Аргументы:

- ``sfConvexShape* shape`` - форма
- ``sfColor color`` - цвет контура

```c
CSFML_GRAPHICS_API void sfConvexShape_setOutlineColor(sfConvexShape* shape, sfColor color);
```
<hr/>

## sfConvexShape_setOutlineThickness - толщина линии контура

Это число не может быть отрицательным. Отключить контур можно установив значение равным 0.

По умолчанию толщина контура равна 0.

Аргументы:

- ``sfConvexShape* shape`` - форма
- ``float thickness`` - толщина контура

```c
CSFML_GRAPHICS_API void sfConvexShape_setOutlineThickness(sfConvexShape* shape, float thickness);
```
<hr/>

## sfConvexShape_getTexture - получить исходную текстуру объекта

Если у фигуры нет исходной текстуры, возвращается NULL-указатель. 

Возвращаемый указатель является константным, и это означает, что изменить текстуру при помощи этой функции нельзя.

Аргументы:

- ``const sfConvexShape* shape`` - форма

**Возвращаемое значение:** ``const sfTexture*`` - текстура

```c
CSFML_GRAPHICS_API const sfTexture* sfConvexShape_getTexture(const sfConvexShape* shape);
```
<hr/>

## sfConvexShape_getTextureRect - получить отображаемую область текстуры

Аргументы:

- ``sfConvexShape* shape`` - форма

**Возвращаемое значение:** ``const sfIntRect`` - область

```c
CSFML_GRAPHICS_API sfIntRect sfConvexShape_getTextureRect(const sfConvexShape* shape);
```
<hr/>

## sfConvexShape_getFillColor - получить цвет заливки

Аргументы:

- ``const sfConvexShape* shape`` - форма

**Возвращаемое значение:** ``sfColor`` - цвет заливки


```c
CSFML_GRAPHICS_API sfColor sfConvexShape_getFillColor(const sfConvexShape* shape);
```
<hr/>

## sfConvexShape_getOutlineColor - получить цвет контура

Аргументы:

- ``const sfConvexShape* shape`` - форма

**Возвращаемое значение:** ``sfColor`` - цвет контура

```c
CSFML_GRAPHICS_API sfColor sfConvexShape_getOutlineColor(const sfConvexShape* shape);
```
<hr/>

## sfConvexShape_getOutlineThickness - получить толшину линии контура

Аргументы:

- ``const sfConvexShape* shape`` - форма

**Возвращаемое значение:** ``float`` - толшина линии контура

```c
CSFML_GRAPHICS_API float sfConvexShape_getOutlineThickness(const sfConvexShape* shape);
```
<hr/>

## sfConvexShape_getPointCount - получить общее количество точек фигуры

Аргументы:

- ``const sfConvexShape* shape`` - форма

**Возвращаемое значение:** ``size_t`` - количество точек (вершин) фигуры

```c
CSFML_GRAPHICS_API size_t sfConvexShape_getPointCount(const sfConvexShape* shape);
```
<hr/>

## sfConvexShape_getPoint - получить точку (вершину)

Аргументы:

- ``const sfConvexShape* shape`` - форма
- ``size_t index`` - индекс точки в диапазоне [0 .. getPointCount() - 1]

**Возвращаемое значение:** ``sfVector2f`` - точка (вершина)

```c
CSFML_GRAPHICS_API sfVector2f sfConvexShape_getPoint(const sfConvexShape* shape, size_t index);
```
<hr/>

## sfConvexShape_setPointCount - установить количество точек формы

Количество точек должно быть не менее 2х.

Готовит форму к произвольной отрисовке.

Аргументы:

- ``const sfConvexShape* shape`` - форма
- ``size_t count`` - количество точек

```c
CSFML_GRAPHICS_API void sfConvexShape_setPointCount(sfConvexShape* shape, size_t count);
```
<hr/>

## sfConvexShape_setPoint - установить точку формы

Точки, по которым рисуется контур.

Аргументы:

- ``const sfConvexShape* shape`` - форма
- ``size_t index`` - индекс точки в диапазоне [0 .. getPointCount() - 1]
- ``sfVector2f point`` - новая точка

```c
CSFML_GRAPHICS_API void sfConvexShape_setPoint(sfConvexShape* shape, size_t index, sfVector2f point);
```
<hr/>

## sfConvexShape_getLocalBounds - получить локальный ограничивающий прямоугольник фигуры

Возвращенный прямоугольник имеет локальные координаты, и это означает, что он игнорирует все преобразования (перемещение, поворот, масштаб и т. д.), применяемые к объекту. 
Другими словами, эта функция возвращает границы объекта в системе его координат.

Аргументы:

- ``const sfConvexShape* shape`` - форма

**Возвращаемое значение:** ``sfFloatRect`` - ограничивающая область

```c
CSFML_GRAPHICS_API sfFloatRect sfConvexShape_getLocalBounds(const sfConvexShape* shape);
```
<hr/>

## sfConvexShape_getGlobalBounds - получить глобальный ограничивающий прямоугольник фигуры

Возвращенный прямоугольник имеет глобальные координаты, и это означает, что он учитывает все преобразования (перемещение, поворот, масштаб и т. Д.), Применяемые к объекту. 
Другими словами, эта функция возвращает границы спрайта в глобальной системе координат 2D-мира.

Аргументы:

- ``const sfConvexShape* shape`` - форма

**Возвращаемое значение:** ``sfFloatRect`` - ограничивающая область


```c
CSFML_GRAPHICS_API sfFloatRect sfConvexShape_getGlobalBounds(const sfConvexShape* shape);
```
<hr/>

```c
#endif // SFML_CONVEXSHAPE_H
```
<hr/>

