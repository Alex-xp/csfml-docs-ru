# CircleShape.h - окружность

```#include <SFML/Graphics/CircleShape.h>```
<hr/>

```c
#ifndef SFML_CIRCLESHAPE_H
#define SFML_CIRCLESHAPE_H

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

## sfCircleShape_create - создать фигуру окружности

**Возвращаемое значение:** ``sfCircleShape*`` - указатель на фигуру (NULL - при неудаче)

```c
CSFML_GRAPHICS_API sfCircleShape* sfCircleShape_create(void);
```
<hr/>

## sfCircleShape_copy - полное копирование фигуры

Аргументы:

- ``const sfCircleShape* shape`` - копируемая фигура

**Возвращаемое значение:** ``sfCircleShape*`` - указатель на копию фигуры (NULL - при неудаче)

```c
CSFML_GRAPHICS_API sfCircleShape* sfCircleShape_copy(const sfCircleShape* shape);
```
<hr/>

## sfCircleShape_destroy - удалить фигуру

Аргументы:

- ``const sfCircleShape* shape`` - удаляемая фигура

```c
CSFML_GRAPHICS_API void sfCircleShape_destroy(sfCircleShape* shape);
```
<hr/>

## sfCircleShape_setPosition - установить позицию

Аргументы:

- ``sfCircleShape* shape`` - прямоугольная фигура
- ``sfVector2f position`` - новая позиция

```c
CSFML_GRAPHICS_API void sfCircleShape_setPosition(sfCircleShape* shape, sfVector2f position);
```
<hr/>

## sfCircleShape_setRotation - установить угол поворота

Полностью переписывает поворот объекта на указанный угол.

По умолчанию угол = 0

Аргументы:

- ``sfCircleShape* shape`` - фигура
- ``float angle`` - угол в градусах

```c
CSFML_GRAPHICS_API void sfCircleShape_setRotation(sfCircleShape* shape, float angle);
```
<hr/>

## sfCircleShape_setScale - установить масштаб

Перезапишет текущий масштаб.

По умолчанию масштаб = (1, 1)

Аргументы:

- ``sfCircleShape* shape`` - фигура
- ``sfVector2f scale`` - масштаб


```c
CSFML_GRAPHICS_API void sfCircleShape_setScale(sfCircleShape* shape, sfVector2f scale);
```
<hr/>

## sfCircleShape_setOrigin - установить относительную точку трансформации 

Исходная точка преобразований для объекта, определяет центральную точку трансформаций (перемещение, масштаб, поворот).
Координаты этой точки обычно устанавливаются относительно верхнего левого угла объекта и не учавствуют в преобразованиях.

Исходная точка преобразований по умолчанию = (0, 0).

Аргументы:

- ``sfCircleShape* shape`` - фигура
- ``sfVector2f origin`` - точка преобразований

```c
CSFML_GRAPHICS_API void sfCircleShape_setOrigin(sfCircleShape* shape, sfVector2f origin);
```
<hr/>

## sfCircleShape_getPosition - получить позицию объекта

Аргументы:

- ``const sfCircleShape* shape`` - фигура

**Возвращаемое значение:** ``sfVector2f`` - позиция

```c
CSFML_GRAPHICS_API sfVector2f sfCircleShape_getPosition(const sfCircleShape* shape);
```
<hr/>

## sfCircleShape_getRotation - получить угол поворота

Аргументы:

- ``const sfCircleShape* shape`` - фигура

**Возвращаемое значение:** ``float`` - угол в градусах

```c
CSFML_GRAPHICS_API float sfCircleShape_getRotation(const sfCircleShape* shape);
```
<hr/>

## sfCircleShape_getScale - получить масштаб объекта

Аргументы:

- ``const sfCircleShape* shape`` - фигура

**Возвращаемое значение:** ``sfVector2f`` - масштаб

```c
CSFML_GRAPHICS_API sfVector2f sfCircleShape_getScale(const sfCircleShape* shape);
```
<hr/>

## sfCircleShape_getOrigin - получить локальную точку трансформации

Локальная точка определяется относительно объекта (относительно левого верхнего угла области объекта).

Аргументы:

- ``const sfCircleShape* shape`` - фигура

**Возвращаемое значение:** ``sfVector2f`` - точка трансформации

```c
CSFML_GRAPHICS_API sfVector2f sfCircleShape_getOrigin(const sfCircleShape* shape);
```
<hr/>

## sfCircleShape_move - перемещение объекта

Аргументы:

- ``sfCircleShape* shape`` - фигура
- ``sfVector2f offset`` - смещение

```c
CSFML_GRAPHICS_API void sfCircleShape_move(sfCircleShape* shape, sfVector2f offset);
```
<hr/>

## sfCircleShape_rotate - повернуть объект

Аргументы:

- ``sfCircleShape* shape`` - фигура
- ``float angle`` - угол поворота в градусах

```c
CSFML_GRAPHICS_API void sfCircleShape_rotate(sfCircleShape* shape, float angle);
```
<hr/>

## sfCircleShape_scale - изменить масштаб объекта

В отличие от sfShape_setScale, эта функция умножает текущий масштаб объекта, а не перезаписывает.

Аргументы:

- ``sfCircleShape* shape`` - фигура
- ``sfVector2f factors`` - масштаб

```c
CSFML_GRAPHICS_API void sfCircleShape_scale(sfCircleShape* shape, sfVector2f factors);
```
<hr/>

## sfCircleShape_getTransform - получить матрицу преобразований объекта

Аргументы:

- ``const sfCircleShape* shape`` - фигура

**Возвращаемое значение:** ``sfTransform`` - матрица преобразований 3x3

```c
CSFML_GRAPHICS_API sfTransform sfCircleShape_getTransform(const sfCircleShape* shape);
```
<hr/>

## sfCircleShape_getInverseTransform - получить обратную матрицу преобразований объекта

Аргументы:

- ``const sfCircleShape* shape`` - фигура

**Возвращаемое значение:** ``sfTransform`` - матрица преобразований 3x3

```c
CSFML_GRAPHICS_API sfTransform sfCircleShape_getInverseTransform(const sfCircleShape* shape);
```
<hr/>

## sfCircleShape_setTexture  - установить исходную текстуру объекта

Объект работает с текстурой в памяти. Текстура представляет собой графический вид объекта. 
Переданная текстура в аргументе данной функции, должна существовать в памяти на протяжении работы объекта.
Если текстуру удалить до окончания работы объекта, может возникнуть ситуация обращения к пустому указателю.

Чтобы отключить текстуру, можно передать NULL.

Аргументы:

- ``sfCircleShape* shape`` - фигура
- ``const sfTexture* texture`` - текстура (или NULL, чтобы отключить текстуру)
- ``sfBool resetRect`` - автоматически подгонять размер объекта под текстуру (sfTrue - заставит объект подогнать свои размеры под под размеры текстуры)

```c
CSFML_GRAPHICS_API void sfCircleShape_setTexture(sfCircleShape* shape, const sfTexture* texture, sfBool resetRect);
```
<hr/>

## sfCircleShape_setTextureRect - отображение части текстуры

При помощи этой функции можно отобразить не всю текстуру целиком, а её часть, описаную прямоугольником.

По умолчанию отображается вся текстура.

Аргументы:

- ``sfCircleShape* shape`` - фигура
- ``sfIntRect rect`` - область отображения

```c
CSFML_GRAPHICS_API void sfCircleShape_setTextureRect(sfCircleShape* shape, sfIntRect rect);
```
<hr/>

## sfCircleShape_setFillColor - цвет заливки

Цвет заливки умножается на цвет текстуры. 

Используя sfTransparent - можно создать прозрачную заливку, оставив только контур.

По умолчанию цвет заливки белый.

Аргументы:

- ``sfCircleShape* shape`` - фигура
- ``sfColor color`` - цвет заливки

```c
CSFML_GRAPHICS_API void sfCircleShape_setFillColor(sfCircleShape* shape, sfColor color);
```
<hr/>

## sfCircleShape_setOutlineColor - цвет контура

Используя sfTransparent - можно создать прозрачный контур.

Аргументы:

- ``sfCircleShape* shape`` - фигура
- ``sfColor color`` - цвет контура

```c
CSFML_GRAPHICS_API void sfCircleShape_setOutlineColor(sfCircleShape* shape, sfColor color);
```
<hr/>

## sfCircleShape_setOutlineThickness - толщина линии контура

Это число не может быть отрицательным. Отключить контур можно установив значение равным 0.

По умолчанию толщина контура равна 0.

Аргументы:

- ``sfCircleShape* shape`` - фигура
- ``float thickness`` - толщина контура

```c
CSFML_GRAPHICS_API void sfCircleShape_setOutlineThickness(sfCircleShape* shape, float thickness);
```
<hr/>

## sfCircleShape_getTexture - получить исходную текстуру объекта

Если у фигуры нет исходной текстуры, возвращается NULL-указатель. 

Возвращаемый указатель является константным, и это означает, что изменить текстуру при помощи этой функции нельзя.

Аргументы:

- ``const sfCircleShape* shape`` - фигура

**Возвращаемое значение:** ``const sfTexture*`` - текстура

```c
CSFML_GRAPHICS_API const sfTexture* sfCircleShape_getTexture(const sfCircleShape* shape);
```
<hr/>

## sfCircleShape_getTextureRect - получить отображаемую область текстуры

Аргументы:

- ``sfCircleShape* shape`` - фигура

**Возвращаемое значение:** ``const sfIntRect`` - область

```c
CSFML_GRAPHICS_API sfIntRect sfCircleShape_getTextureRect(const sfCircleShape* shape);
```
<hr/>

## sfCircleShape_getFillColor - получить цвет заливки

Аргументы:

- ``const sfCircleShape* shape`` - фигура

**Возвращаемое значение:** ``sfColor`` - цвет заливки

```c
CSFML_GRAPHICS_API sfColor sfCircleShape_getFillColor(const sfCircleShape* shape);
```
<hr/>

## sfCircleShape_getOutlineColor - получить цвет контура

Аргументы:

- ``const sfCircleShape* shape`` - фигура

**Возвращаемое значение:** ``sfColor`` - цвет контура

```c
CSFML_GRAPHICS_API sfColor sfCircleShape_getOutlineColor(const sfCircleShape* shape);
```
<hr/>

## sfCircleShape_getOutlineThickness - получить толшину линии контура

Аргументы:

- ``const sfCircleShape* shape`` - фигура

**Возвращаемое значение:** ``float`` - толшина линии контура

```c
CSFML_GRAPHICS_API float sfCircleShape_getOutlineThickness(const sfCircleShape* shape);
```
<hr/>

## sfCircleShape_getPointCount - получить общее количество точек фигуры

Аргументы:

- ``const sfCircleShape* shape`` - фигура

**Возвращаемое значение:** ``size_t`` - количество точек (вершин) фигуры

```c
CSFML_GRAPHICS_API size_t sfCircleShape_getPointCount(const sfCircleShape* shape);
```
<hr/>

## sfCircleShape_getPoint - получить точку (вершину)

Аргументы:

- ``const sfCircleShape* shape`` - фигура
- ``size_t index`` - индекс точки в диапазоне [0 .. getPointCount() - 1]

**Возвращаемое значение:** ``sfVector2f`` - точка (вершина)

```c
CSFML_GRAPHICS_API sfVector2f sfCircleShape_getPoint(const sfCircleShape* shape, size_t index);
```
<hr/>

## sfCircleShape_setRadius - установить радиус в пикселях

Аргументы:

- ``sfCircleShape* shape`` - фигура
- ``float radius`` - радиус в пикселях

```c
CSFML_GRAPHICS_API void sfCircleShape_setRadius(sfCircleShape* shape, float radius);
```
<hr/>

## sfCircleShape_getRadius - получить радиус в пикселях

Аргументы:

- ``sfCircleShape* shape`` - фигура

**Возвращаемое значение:** ``float`` - радиус в пикселях

```c
CSFML_GRAPHICS_API float sfCircleShape_getRadius(const sfCircleShape* shape);
```
<hr/>

## sfCircleShape_setPointCount - установить количество точек на окружность (детализация)

Аргументы:

- ``sfCircleShape* shape`` - фигура
- ``size_t count`` - количество точек на окружность

```c
CSFML_GRAPHICS_API void sfCircleShape_setPointCount(sfCircleShape* shape, size_t count);
```
<hr/>

## sfCircleShape_getLocalBounds - получить локальный ограничивающий прямоугольник фигуры

Возвращенный прямоугольник имеет локальные координаты, и это означает, что он игнорирует все преобразования (перемещение, поворот, масштаб и т. д.), применяемые к объекту. 
Другими словами, эта функция возвращает границы объекта в системе его координат.

Аргументы:

- ``const sfCircleShape* shape`` - фигура

**Возвращаемое значение:** ``sfFloatRect`` - ограничивающая область

```c
CSFML_GRAPHICS_API sfFloatRect sfCircleShape_getLocalBounds(const sfCircleShape* shape);
```
<hr/>

## sfCircleShape_getGlobalBounds - получить глобальный ограничивающий прямоугольник фигуры

Возвращенный прямоугольник имеет глобальные координаты, и это означает, что он учитывает все преобразования (перемещение, поворот, масштаб и т. Д.), Применяемые к объекту. Другими словами, эта функция возвращает границы спрайта в глобальной системе координат 2D-мира.

Аргументы:

- ``const sfCircleShape* shape`` - фигура

**Возвращаемое значение:** ``sfFloatRect`` - ограничивающая область

```c
CSFML_GRAPHICS_API sfFloatRect sfCircleShape_getGlobalBounds(const sfCircleShape* shape);
```
<hr/>

```c
#endif // SFML_CIRCLESHAPE_H
```
<hr/>

