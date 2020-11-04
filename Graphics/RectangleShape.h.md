# RectangleShape.h - прямоугольная фигура

```#include <SFML/Graphics/RectangleShape.h>```
<hr/>

```c
#ifndef SFML_RECTANGLESHAPE_H
#define SFML_RECTANGLESHAPE_H

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

## sfRectangleShape_create - создать прямоугольную фигуру

**Возвращаемое значение:** ``sfRectangleShape*`` - указатель на фигуру (NULL - при неудаче)

```c
CSFML_GRAPHICS_API sfRectangleShape* sfRectangleShape_create(void);
```
<hr/>

## sfRectangleShape_copy - полное копирование прямоугольной фигуры

Аргументы:

- ``const sfRectangleShape* shape`` - копируемая фигура

**Возвращаемое значение:** ``sfRectangleShape*`` - указатель на копию фигуры (NULL - при неудаче)

```c
CSFML_GRAPHICS_API sfRectangleShape* sfRectangleShape_copy(const sfRectangleShape* shape);
```
<hr/>

## sfRectangleShape_destroy - удалить прямоугольную фигуру

Аргументы:

- ``const sfRectangleShape* shape`` - прямоугольная фигура

```c
CSFML_GRAPHICS_API void sfRectangleShape_destroy(sfRectangleShape* shape);
```
<hr/>

## sfRectangleShape_setPosition - установить позицию

Аргументы:

- ``sfRectangleShape* shape`` - прямоугольная фигура
- ``sfVector2f position`` - новая позиция

```c
CSFML_GRAPHICS_API void sfRectangleShape_setPosition(sfRectangleShape* shape, sfVector2f position);
```
<hr/>

## sfRectangleShape_setRotation - установить угол поворота

Полностью переписывает поворот объекта на указанный угол.

По умолчанию угол = 0

Аргументы:

- ``sfRectangleShape* shape`` - фигура
- ``float angle`` - угол в градусах
```c
CSFML_GRAPHICS_API void sfRectangleShape_setRotation(sfRectangleShape* shape, float angle);
```
<hr/>

## sfRectangleShape_setScale - установить масштаб

Перезапишет текущий масштаб.

По умолчанию масштаб = (1, 1)

Аргументы:

- ``sfRectangleShape* shape`` - фигура
- ``sfVector2f scale`` - масштаб

```c
CSFML_GRAPHICS_API void sfRectangleShape_setScale(sfRectangleShape* shape, sfVector2f scale);
```
<hr/>

## sfRectangleShape_setOrigin - установить относительную точку трансформации 

Исходная точка преобразований для объекта, определяет центральную точку трансформаций (перемещение, масштаб, поворот).
Координаты этой точки обычно устанавливаются относительно верхнего левого угла объекта и не учавствуют в преобразованиях.

Исходная точка преобразований по умолчанию = (0, 0).

Аргументы:

- ``sfRectangleShape* shape`` - фигура
- ``sfVector2f origin`` - точка преобразований

```c
CSFML_GRAPHICS_API void sfRectangleShape_setOrigin(sfRectangleShape* shape, sfVector2f origin);
```
<hr/>

## sfShape_getPosition - получить позицию объекта

Аргументы:

- ``sfRectangleShape* shape`` - фигура

**Возвращаемое значение:** ``sfVector2f`` - позиция

```c
CSFML_GRAPHICS_API sfVector2f sfRectangleShape_getPosition(const sfRectangleShape* shape);
```
<hr/>

## sfRectangleShape_getRotation - получить угол поворота

Аргументы:

- ``const sfRectangleShape* shape`` - фигура

**Возвращаемое значение:** ``float`` - угол в градусах

```c
CSFML_GRAPHICS_API float sfRectangleShape_getRotation(const sfRectangleShape* shape);
```
<hr/>

## sfRectangleShape_getScale - получить масштаб объекта

Аргументы:

- ``const sfRectangleShape* shape`` - фигура

**Возвращаемое значение:** ``sfVector2f`` - масштаб

```c
CSFML_GRAPHICS_API sfVector2f sfRectangleShape_getScale(const sfRectangleShape* shape);
```
<hr/>

## sfRectangleShape_getOrigin - получить локальную точку трансформации

Локальная точка определяется относительно объекта (относительно левого верхнего угла области объекта).

Аргументы:

- ``const sfRectangleShape* shape`` - фигура

**Возвращаемое значение:** ``sfVector2f`` - точка трансформации

```c
CSFML_GRAPHICS_API sfVector2f sfRectangleShape_getOrigin(const sfRectangleShape* shape);
```
<hr/>

## sfRectangleShape_move - перемещение объекта

Аргументы:

- ``sfRectangleShape* shape`` - фигура
- ``sfVector2f offset`` - смещение

```c
CSFML_GRAPHICS_API void sfRectangleShape_move(sfRectangleShape* shape, sfVector2f offset);
```
<hr/>

## sfRectangleShape_rotate - повернуть объект

Аргументы:

- ``sfShape* shape`` - фигура
- ``float angle`` - угол поворота в градусах

```c
CSFML_GRAPHICS_API void sfRectangleShape_rotate(sfRectangleShape* shape, float angle);
```
<hr/>

## sfRectangleShape_scale - изменить масштаб объекта

В отличие от sfShape_setScale, эта функция умножает текущий масштаб объекта, а не перезаписывает.

Аргументы:

- ``sfRectangleShape* shape`` - фигура
- ``sfVector2f factors`` - масштаб

```c
CSFML_GRAPHICS_API void sfRectangleShape_scale(sfRectangleShape* shape, sfVector2f factors);
```
<hr/>

## sfRectangleShape_getTransform - получить матрицу преобразований объекта

Аргументы:

- ``const sfRectangleShape* shape`` - фигура

**Возвращаемое значение:** ``sfTransform`` - матрица преобразований 3x3

```c
CSFML_GRAPHICS_API sfTransform sfRectangleShape_getTransform(const sfRectangleShape* shape);
```
<hr/>

## sfRectangleShape_getInverseTransform - получить обратную матрицу преобразований объекта

Аргументы:

- ``const sfRectangleShape* shape`` - фигура

**Возвращаемое значение:** ``sfTransform`` - матрица преобразований 3x3

```c
CSFML_GRAPHICS_API sfTransform sfRectangleShape_getInverseTransform(const sfRectangleShape* shape);
```
<hr/>

## sfRectangleShape_setTexture  - установить исходную текстуру объекта

Объект работает с текстурой в памяти. Текстура представляет собой графический вид объекта. 
Переданная текстура в аргументе данной функции, должна существовать в памяти на протяжении работы объекта.
Если текстуру удалить до окончания работы объекта, может возникнуть ситуация обращения к пустому указателю.

Чтобы отключить текстуру, можно передать NULL.

Аргументы:

- ``sfRectangleShape* shape`` - фигура
- ``const sfTexture* texture`` - текстура (или NULL, чтобы отключить текстуру)
- ``sfBool resetRect`` - автоматически подгонять размер объекта под текстуру (sfTrue - заставит объект подогнать свои размеры под под размеры текстуры)

```c
CSFML_GRAPHICS_API void sfRectangleShape_setTexture(sfRectangleShape* shape, const sfTexture* texture, sfBool resetRect);
```
<hr/>

## sfRectangleShape_setTextureRect - отображение части текстуры

При помощи этой функции можно отобразить не всю текстуру целиком, а её часть, описаную прямоугольником.

По умолчанию отображается вся текстура.

Аргументы:

- ``sfShape* shape`` - фигура
- ``sfIntRect rect`` - область отображения

```c
CSFML_GRAPHICS_API void sfRectangleShape_setTextureRect(sfRectangleShape* shape, sfIntRect rect);
```
<hr/>

## sfRectangleShape_setFillColor - цвет заливки

Цвет заливки умножается на цвет текстуры. 

Используя sfTransparent - можно создать прозрачную заливку, оставив только контур.

По умолчанию цвет заливки белый.

Аргументы:

- ``sfRectangleShape* shape`` - фигура
- ``sfColor color`` - цвет заливки

```c
CSFML_GRAPHICS_API void sfRectangleShape_setFillColor(sfRectangleShape* shape, sfColor color);
```
<hr/>

## sfRectangleShape_setOutlineColor - цвет контура

Используя sfTransparent - можно создать прозрачный контур.

Аргументы:

- ``sfRectangleShape* shape`` - фигура
- ``sfColor color`` - цвет контура

```c
CSFML_GRAPHICS_API void sfRectangleShape_setOutlineColor(sfRectangleShape* shape, sfColor color);
```
<hr/>

## sfRectangleShape_setOutlineThickness - толщина линии контура

Это число не может быть отрицательным. Отключить контур можно установив значение равным 0.

По умолчанию толщина контура равна 0.

Аргументы:

- ``sfRectangleShape* shape`` - фигура
- ``float thickness`` - толщина контура

```c
CSFML_GRAPHICS_API void sfRectangleShape_setOutlineThickness(sfRectangleShape* shape, float thickness);
```
<hr/>

## sfRectangleShape_getTexture - получить исходную текстуру объекта

Если у фигуры нет исходной текстуры, возвращается NULL-указатель. 

Возвращаемый указатель является константным, и это означает, что изменить текстуру при помощи этой функции нельзя.

Аргументы:

- ``const sfRectangleShape* shape`` - фигура

**Возвращаемое значение:** ``const sfTexture*`` - текстура

```c
CSFML_GRAPHICS_API const sfTexture* sfRectangleShape_getTexture(const sfRectangleShape* shape);
```
<hr/>

## sfRectangleShape_getTextureRect - получить отображаемую область текстуры

Аргументы:

- ``sfRectangleShape* shape`` - фигура

**Возвращаемое значение:** ``const sfIntRect`` - область

```c
CSFML_GRAPHICS_API sfIntRect sfRectangleShape_getTextureRect(const sfRectangleShape* shape);
```
<hr/>

## sfRectangleShape_getFillColor - получить цвет заливки

Аргументы:

- ``const sfRectangleShape* shape`` - фигура

**Возвращаемое значение:** ``sfColor`` - цвет заливки

```c
CSFML_GRAPHICS_API sfColor sfRectangleShape_getFillColor(const sfRectangleShape* shape);
```
<hr/>

## sfRectangleShape_getOutlineColor - получить цвет контура

Аргументы:

- ``const sfRectangleShape* shape`` - фигура

**Возвращаемое значение:** ``sfColor`` - цвет контура

```c
CSFML_GRAPHICS_API sfColor sfRectangleShape_getOutlineColor(const sfRectangleShape* shape);
```
<hr/>

## sfRectangleShape_getOutlineThickness - получить толшину линии контура

Аргументы:

- ``const sfRectangleShape* shape`` - фигура

**Возвращаемое значение:** ``float`` - толшина линии контура

```c
CSFML_GRAPHICS_API float sfRectangleShape_getOutlineThickness(const sfRectangleShape* shape);
```
<hr/>

## sfRectangleShape_getPointCount - получить общее количество точек фигуры

Аргументы:

- ``const sfRectangleShape* shape`` - фигура

**Возвращаемое значение:** ``size_t`` - количество точек (вершин) фигуры

```c
CSFML_GRAPHICS_API size_t sfRectangleShape_getPointCount(const sfRectangleShape* shape);
```
<hr/>

## sfRectangleShape_getPoint - получить точку (вершину)

Аргументы:

- ``const sfRectangleShape* shape`` - фигура
- ``size_t index`` - индекс точки в диапазоне [0 .. getPointCount() - 1]

**Возвращаемое значение:** ``sfVector2f`` - точка (вершина)

```c
CSFML_GRAPHICS_API sfVector2f sfRectangleShape_getPoint(const sfRectangleShape* shape, size_t index);
```
<hr/>

## sfRectangleShape_setSize - установить размер фигуры в пикселях

Аргументы:

- ``sfRectangleShape* shape`` - фигура
- ``sfVector2f size`` - размер фигуры в пикселях

```c
CSFML_GRAPHICS_API void sfRectangleShape_setSize(sfRectangleShape* shape, sfVector2f size);
```
<hr/>

## sfRectangleShape_getSize - получить размер фигуры в пикселях

Аргументы:

- ``const sfRectangleShape* shape`` - фигура

**Возвращаемое значение:** ``sfVector2f`` - размер фигуры в пикселях

```c
CSFML_GRAPHICS_API sfVector2f sfRectangleShape_getSize(const sfRectangleShape* shape);
```
<hr/>

## sfRectangleShape_getLocalBounds - получить локальный ограничивающий прямоугольник фигуры

Возвращенный прямоугольник имеет локальные координаты, и это означает, что он игнорирует все преобразования (перемещение, поворот, масштаб и т. д.), применяемые к объекту. Другими словами, эта функция возвращает границы объекта в системе его координат.

Аргументы:

- ``const sfRectangleShape* shape`` - фигура

**Возвращаемое значение:** ``sfFloatRect`` - ограничивающая область

```c
CSFML_GRAPHICS_API sfFloatRect sfRectangleShape_getLocalBounds(const sfRectangleShape* shape);
```
<hr/>

## sfRectangleShape_getGlobalBounds - получить глобальный ограничивающий прямоугольник фигуры

Возвращенный прямоугольник имеет глобальные координаты, и это означает, что он учитывает все преобразования (перемещение, поворот, масштаб и т. Д.), Применяемые к объекту. Другими словами, эта функция возвращает границы спрайта в глобальной системе координат 2D-мира.

Аргументы:

- ``const sfRectangleShape* shape`` - фигура

**Возвращаемое значение:** ``sfFloatRect`` - ограничивающая область

```c
CSFML_GRAPHICS_API sfFloatRect sfRectangleShape_getGlobalBounds(const sfRectangleShape* shape);
```
<hr/>

```c
#endif // SFML_RECTANGLESHAPE_H
```

