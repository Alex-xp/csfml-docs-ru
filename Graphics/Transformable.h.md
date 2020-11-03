# Transformable.h - изменяемость

```#include <SFML/Graphics/Transformable.h>```

Более точно - это ручка управления преобразованиями.

Все функции преобразования, работают с объектом управления изменяя его состояние.

<hr/>

```c
#ifndef SFML_TRANSFORMABLE_H
#define SFML_TRANSFORMABLE_H

////////////////////////////////////////////////////////////
// Headers
////////////////////////////////////////////////////////////
#include <SFML/Graphics/Export.h>
#include <SFML/Graphics/Types.h>
#include <SFML/Graphics/Transform.h>
#include <SFML/System/Vector2.h>
```
<hr/>

## sfTransformable_create - создать объект изменяемости

Создает ручку управления трансформацией объекта.
Упрощает преобразования объектов.

**Возвращаемое значение:** ``sfTransformable*`` - указатель на объект управления трансформацией.

```c
CSFML_GRAPHICS_API sfTransformable* sfTransformable_create(void);
```
<hr/>

## sfTransformable_copy - полное копирование объекта управления

Аргументы:

- ``const sfTransformable* transformable`` - копируемый объект

**Возвращаемое значение:** ``sfTransformable*`` - указатель на новый объект управления трансформацией.

```c
CSFML_GRAPHICS_API sfTransformable* sfTransformable_copy(const sfTransformable* transformable);
```
<hr/>

## sfTransformable_destroy - удалить объект управления

Аргументы:

- ``sfTransformable* transformable`` - удаляемый объект

```c
CSFML_GRAPHICS_API void sfTransformable_destroy(sfTransformable* transformable);
```
<hr/>

## sfTransformable_setPosition - установить точку трансформации

Позволяет применять преобразования от указанной точки (например, поворот вокруг произвольной точки).

По умолчанию, точка равна (0,0).

Аргументы:

- ``sfTransformable* transformable`` - объект управления
- ``sfVector2f position`` - точка трансформации

```c
CSFML_GRAPHICS_API void sfTransformable_setPosition(sfTransformable* transformable, sfVector2f position);
```
<hr/>

## sfTransformable_setRotation - установить поворот

Полностью переписывает поворот объекта на указанный угол.

По умолчанию угол = 0

Аргументы:

- ``sfTransformable* transformable`` - объект управления
- ``float angle`` - угол поворота

```c
CSFML_GRAPHICS_API void sfTransformable_setRotation(sfTransformable* transformable, float angle);
```
<hr/>

## sfTransformable_setScale - установить масштаб

По умолчанию масштаб = (1, 1)

Аргументы:

- ``sfTransformable* transformable`` - объект управления
- ``sfVector2f scale`` - масштаб


```c
CSFML_GRAPHICS_API void sfTransformable_setScale(sfTransformable* transformable, sfVector2f scale);
```
<hr/>

## sfTransformable_setOrigin - установить относительную точку трансформации 

Исходная точка преобразований для объекта, определяет центральную точку трансформаций (перемещение, масштаб, поворот).
Координаты этой точки обычно устанавливаются относительно верхнего левого угла объекта и не учавствуют в преобразованиях.

Исходная точка преобразований по умолчанию = (0, 0).

Аргументы:

- ``sfTransformable* transformable`` - объект управления
- ``sfVector2f position`` - точка преобразований

```c
CSFML_GRAPHICS_API void sfTransformable_setOrigin(sfTransformable* transformable, sfVector2f origin);
```
<hr/>

## sfTransformable_getPosition - получить точку трансформации

Аргументы:

- ``const sfTransformable* transformable`` - объект управления

**Возвращаемое значение:** ``sfVector2f`` - точка трансформации

```c
CSFML_GRAPHICS_API sfVector2f sfTransformable_getPosition(const sfTransformable* transformable);
```
<hr/>

## sfTransformable_getRotation - получить угол поворота

Аргументы:

- ``const sfTransformable* transformable`` - объект управления

**Возвращаемое значение:** ``float`` - угол (0 .. 360)

```c
CSFML_GRAPHICS_API float sfTransformable_getRotation(const sfTransformable* transformable);
```
<hr/>

## sfTransformable_getScale - получить масштаб

Аргументы:

- ``const sfTransformable* transformable`` - объект управления

**Возвращаемое значение:** ``sfVector2f`` - масштаб по осям

```c
CSFML_GRAPHICS_API sfVector2f sfTransformable_getScale(const sfTransformable* transformable);
```
<hr/>

## sfTransformable_getOrigin - получить относительную точку трансформации 

Аргументы:

- ``const sfTransformable* transformable`` - объект управления

**Возвращаемое значение:** ``sfVector2f`` - относительная точка трансформации 

```c
CSFML_GRAPHICS_API sfVector2f sfTransformable_getOrigin(const sfTransformable* transformable);
```
<hr/>

## sfTransformable_move - перемещение

Аргументы:

- ``sfTransformable* transformable`` - объект управления
- ``sfVector2f offset`` - координаты смещения

```c
CSFML_GRAPHICS_API void sfTransformable_move(sfTransformable* transformable, sfVector2f offset);
```
<hr/>

## sfTransformable_rotate - повернуть объект

Аргументы:

- ``sfTransformable* transformable`` - объект управления
- ``float angle`` - угол поворота в градусах

```c
CSFML_GRAPHICS_API void sfTransformable_rotate(sfTransformable* transformable, float angle);
```
<hr/>

## sfTransformable_scale - масштабировать

Аргументы:

- ``sfTransformable* transformable`` - объект управления
- ``sfVector2f factors`` - масштабирование по осям

```c
CSFML_GRAPHICS_API void sfTransformable_scale(sfTransformable* transformable, sfVector2f factors);
```
<hr/>

## sfTransformable_getTransform - получить матрицу sfTransform

Аргументы:

- ``const sfTransformable* transformable`` - объект управления

**Возвращаемое значение:** ``sfTransform`` - матрица преобразований 3x3

```c
CSFML_GRAPHICS_API sfTransform sfTransformable_getTransform(const sfTransformable* transformable);
```
<hr/>

## sfTransformable_getInverseTransform - получить обратную матрицу преобразований

Аргументы:

- ``const sfTransformable* transformable`` - объект управления

**Возвращаемое значение:** ``sfTransform`` - матрица преобразований 3x3

```c
CSFML_GRAPHICS_API sfTransform sfTransformable_getInverseTransform(const sfTransformable* transformable);
```
<hr/>

```c
#endif // SFML_TRANSFORMABLE_H

```
<hr/>

