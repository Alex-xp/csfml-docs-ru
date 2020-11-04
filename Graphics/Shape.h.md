# Shape.h - простая геометрическая фигура

Это бызовое описание фигуры, и её функции должны браться как базовые при создании новой фигуры.

```#include <SFML/Graphics/Shape.h>```
<hr/>

```c
#ifndef SFML_SHAPE_H
#define SFML_SHAPE_H

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

## Определения типов для базовых методов фируры

```c
typedef size_t (*sfShapeGetPointCountCallback)(void*);        ///< Функция, которая должна вернуть количество вершин фигуры
typedef sfVector2f (*sfShapeGetPointCallback)(size_t, void*); ///< Функция, которая должна вернуть вершину по её индексу
```
<hr/>

## sfShape_create - создает новую фигуру

Аргументы:

- ``sfShapeGetPointCountCallback getPointCount`` - метод, подсчитывающий количество точек фигуры
- ``sfShapeGetPointCallback getPoint`` - метод получения точки по индексу
- ``void* userData`` - пользовательские данные

**Возвращаемое значение:** ``sfShape*`` - указатель на фигуру

```c
CSFML_GRAPHICS_API sfShape* sfShape_create(sfShapeGetPointCountCallback getPointCount,
                                           sfShapeGetPointCallback getPoint,
                                           void* userData);
```
<hr/>

## sfShape_destroy - удалить фигуру

Аргументы:

- ``sfShape* shape`` - фигура

```c
CSFML_GRAPHICS_API void sfShape_destroy(sfShape* shape);
```
<hr/>

## sfShape_setPosition - установить позицию

Аргументы:

- ``sfShape* shape`` - фигура
- ``sfVector2f position`` - новая позиция

```c
CSFML_GRAPHICS_API void sfShape_setPosition(sfShape* shape, sfVector2f position);
```
<hr/>

## sfShape_setRotation - установить угол поворота

Полностью переписывает поворот объекта на указанный угол.

По умолчанию угол = 0

Аргументы:

- ``sfShape* shape`` - фигура
- ``float angle`` - угол в градусах

```c
CSFML_GRAPHICS_API void sfShape_setRotation(sfShape* shape, float angle);
```
<hr/>

## sfShape_setScale - установить масштаб

Перезапишет текущий масштаб.

По умолчанию масштаб = (1, 1)

Аргументы:

- ``sfShape* shape`` - фигура
- ``sfVector2f scale`` - масштаб

```c
CSFML_GRAPHICS_API void sfShape_setScale(sfShape* shape, sfVector2f scale);
```
<hr/>

## sfShape_setOrigin - установить относительную точку трансформации 

Исходная точка преобразований для объекта, определяет центральную точку трансформаций (перемещение, масштаб, поворот).
Координаты этой точки обычно устанавливаются относительно верхнего левого угла объекта и не учавствуют в преобразованиях.

Исходная точка преобразований по умолчанию = (0, 0).

Аргументы:

- ``sfShape* shape`` - фигура
- ``sfVector2f position`` - точка преобразований

```c
CSFML_GRAPHICS_API void sfShape_setOrigin(sfShape* shape, sfVector2f origin);
```
<hr/>

## sfShape_getPosition - получить позицию объекта

Аргументы:

- ``sfShape* shape`` - фигура

**Возвращаемое значение:** ``sfVector2f`` - позиция

```c
CSFML_GRAPHICS_API sfVector2f sfShape_getPosition(const sfShape* shape);
```
<hr/>

## sfShape_getRotation - получить угол поворота

Аргументы:

- ``sfShape* shape`` - фигура

**Возвращаемое значение:** ``float`` - угол в градусах

```c
CSFML_GRAPHICS_API float sfShape_getRotation(const sfShape* shape);
```
<hr/>

## sfShape_getScale - получить масштаб объекта

Аргументы:

- ``sfShape* shape`` - фигура

**Возвращаемое значение:** ``sfVector2f`` - масштаб

```c
CSFML_GRAPHICS_API sfVector2f sfShape_getScale(const sfShape* shape);
```
<hr/>

## sfShape_getOrigin - получить локальную точку трансформации

Локальная точка определяется относительно объекта (относительно левого верхнего угла области объекта).

Аргументы:

- ``sfShape* shape`` - фигура

**Возвращаемое значение:** ``sfVector2f`` - точка трансформации

```c
CSFML_GRAPHICS_API sfVector2f sfShape_getOrigin(const sfShape* shape);
```
<hr/>

## sfShape_move - перемещение объекта

Аргументы:

- ``sfShape* shape`` - фигура
- ``sfVector2f offset`` - смещение

```c
CSFML_GRAPHICS_API void sfShape_move(sfShape* shape, sfVector2f offset);
```
<hr/>

## sfShape_rotate - повернуть объект

Аргументы:

- ``sfShape* shape`` - фигура
- ``float angle`` - угол поворота в градусах

```c
CSFML_GRAPHICS_API void sfShape_rotate(sfShape* shape, float angle);
```
<hr/>

## sfShape_scale 

В отличие от sfShape_setScale, эта функция умножает текущий масштаб объекта, а не перезаписывает.

Аргументы:

- ``sfShape* shape`` - фигура
- ``sfVector2f factors`` - масштаб

```c
CSFML_GRAPHICS_API void sfShape_scale(sfShape* shape, sfVector2f factors);
```
<hr/>

## sfTransform - получить матрицу преобразований объекта

Аргументы:

- ``sfShape* shape`` - фигура

**Возвращаемое значение:** ``sfTransform`` - матрица преобразований 3x3

```c
CSFML_GRAPHICS_API sfTransform sfShape_getTransform(const sfShape* shape);
```
<hr/>

## sfShape_getInverseTransform - получить обратную матрицу преобразований объекта

Аргументы:

- ``sfShape* shape`` - фигура

**Возвращаемое значение:** ``sfTransform`` - матрица преобразований 3x3

```c
CSFML_GRAPHICS_API sfTransform sfShape_getInverseTransform(const sfShape* shape);
```
<hr/>

## sfShape_setTexture - установить исходную текстуру объекта

Объект работает с текстурой в памяти. Текстура представляет собой графический вид объекта. 
Переданная текстура в аргументе данной функции, должна существовать в памяти на протяжении работы объекта.
Если текстуру удалить до окончания работы объекта, может возникнуть ситуация обращения к пустому указателю.

Чтобы отключить текстуру, можно передать NULL.

Аргументы:

- ``sfShape* shape`` - фигура
- ``const sfTexture* texture`` - текстура (или NULL, чтобы отключить текстуру)
- ``sfBool resetRect`` - автоматически подгонять размер объекта под текстуру (sfTrue - заставит объект подогнать свои размеры под под размеры текстуры)


```c
CSFML_GRAPHICS_API void sfShape_setTexture(sfShape* shape, const sfTexture* texture, sfBool resetRect);
```
<hr/>

## sfShape_setTextureRect - отображение части текстуры

При помощи этой функции можно отобразить не всю текстуру целиком, а её часть, описаную прямоугольником.

По умолчанию отображается вся текстура.

Аргументы:

- ``sfShape* shape`` - фигура
- ``sfIntRect rect`` - область отображения

```c
CSFML_GRAPHICS_API void sfShape_setTextureRect(sfShape* shape, sfIntRect rect);
```
<hr/>

## sfShape_setFillColor - цвет заливки

Цвет заливки умножается на цвет текстуры. 

Используя sfTransparent - можно создать прозрачную заливку, оставив только контур.

По умолчанию цвет заливки белый.

Аргументы:

- ``sfShape* shape`` - фигура
- ``sfColor color`` - цвет заливки


```c
CSFML_GRAPHICS_API void sfShape_setFillColor(sfShape* shape, sfColor color);
```
<hr/>

## sfShape_setOutlineColor - цвет контура

Используя sfTransparent - можно создать прозрачный контур.

Аргументы:

- ``sfShape* shape`` - фигура
- ``sfColor color`` - цвет контура

```c
CSFML_GRAPHICS_API void sfShape_setOutlineColor(sfShape* shape, sfColor color);
```
<hr/>

## sfShape_setOutlineThickness - толщина линии контура

Это число не может быть отрицательным. Отключить контур можно установив значение равным 0.

По умолчанию толщина контура равна 0.

Аргументы:

- ``sfShape* shape`` - фигура
- ``float thickness`` - толщина контура

```c
CSFML_GRAPHICS_API void sfShape_setOutlineThickness(sfShape* shape, float thickness);
```
<hr/>

## sfShape_getTexture - получить исходную текстуру объекта

Если у фигуры нет исходной текстуры, возвращается NULL-указатель. 

Возвращаемый указатель является константным, и это означает, что изменить текстуру при помощи этой функции нельзя.

Аргументы:

- ``const sfShape* shape`` - фигура

**Возвращаемое значение:** ``const sfTexture*`` - текстура

```c
CSFML_GRAPHICS_API const sfTexture* sfShape_getTexture(const sfShape* shape);
```
<hr/>

## sfShape_getTextureRect - получить отображаемую область текстуры

Аргументы:

- ``sfShape* shape`` - фигура

**Возвращаемое значение:** ``const sfIntRect`` - область

```c
CSFML_GRAPHICS_API sfIntRect sfShape_getTextureRect(const sfShape* shape);
```
<hr/>

## sfShape_getFillColor - получить цвет заливки

Аргументы:

- ``const sfShape* shape`` - фигура

**Возвращаемое значение:** ``sfColor`` - цвет заливки

```c
CSFML_GRAPHICS_API sfColor sfShape_getFillColor(const sfShape* shape);
```
<hr/>

## sfShape_getOutlineColor - получить цвет контура

Аргументы:

- ``const sfShape* shape`` - фигура

**Возвращаемое значение:** ``sfColor`` - цвет контура

```c
CSFML_GRAPHICS_API sfColor sfShape_getOutlineColor(const sfShape* shape);
```
<hr/>

## sfShape_getOutlineThickness - получить толшину линии контура

Аргументы:

- ``const sfShape* shape`` - фигура

**Возвращаемое значение:** ``float`` - толшина линии контура

```c
CSFML_GRAPHICS_API float sfShape_getOutlineThickness(const sfShape* shape);
```
<hr/>

## sfShape_getPointCount - получить общее количество точек фигуры

Аргументы:

- ``const sfShape* shape`` - фигура

**Возвращаемое значение:** ``size_t`` - количество точек (вершин) фигуры

```c
CSFML_GRAPHICS_API size_t sfShape_getPointCount(const sfShape* shape);
```
<hr/>

## sfShape_getPoint - получить точку (вершину)

Аргументы:

- ``const sfShape* shape`` - фигура
- ``size_t index`` - индекс точки в диапазоне [0 .. getPointCount() - 1]

**Возвращаемое значение:** ``sfVector2f`` - точка (вершина)

```c
CSFML_GRAPHICS_API sfVector2f sfShape_getPoint(const sfShape* shape, size_t index);
```
<hr/>

## sfShape_getLocalBounds - получить локальный ограничивающий прямоугольник фигуры

Возвращенный прямоугольник имеет локальные координаты, и это означает, что он игнорирует все преобразования (перемещение, поворот, масштаб и т. д.), применяемые к объекту. Другими словами, эта функция возвращает границы объекта в системе его координат.

Аргументы:

- ``const sfShape* shape`` - фигура

**Возвращаемое значение:** ``sfFloatRect`` - ограничивающая область

```c
CSFML_GRAPHICS_API sfFloatRect sfShape_getLocalBounds(const sfShape* shape);
```
<hr/>

## sfShape_getGlobalBounds - получить глобальный ограничивающий прямоугольник фигуры

Возвращенный прямоугольник имеет глобальные координаты, и это означает, что он учитывает все преобразования (перемещение, поворот, масштаб и т. Д.), Применяемые к объекту. Другими словами, эта функция возвращает границы спрайта в глобальной системе координат 2D-мира.

Аргументы:

- ``const sfShape* shape`` - фигура

**Возвращаемое значение:** ``sfFloatRect`` - ограничивающая область

```c
CSFML_GRAPHICS_API sfFloatRect sfShape_getGlobalBounds(const sfShape* shape);
```
<hr/>

## sfShape_update - обновить и перерисовать фигуру

Следует вызывать только при изменении геометрии или размеров.

```c
CSFML_GRAPHICS_API void sfShape_update(sfShape* shape);
```
<hr/>

```c
#endif // SFML_SHAPE_H
```
<hr/>

