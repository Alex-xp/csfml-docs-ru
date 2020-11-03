# Transform.h - преобразования

```#include <SFML/Graphics/Transform.h>```
<hr/>

```c
#ifndef SFML_TRANSFORM_H
#define SFML_TRANSFORM_H

////////////////////////////////////////////////////////////
// Headers
////////////////////////////////////////////////////////////
#include <SFML/Graphics/Export.h>
#include <SFML/Graphics/Rect.h>
#include <SFML/Graphics/Types.h>
#include <SFML/System/Vector2.h>
```
<hr/>

## sfTransform - матрица преобразований 3x3

```c
typedef struct
{
    float matrix[9];
} sfTransform;
```
<hr/>

## sfTransform_Identity - единичная матрица (база)

```c
CSFML_GRAPHICS_API const sfTransform sfTransform_Identity;
```
<hr/>

## sfTransform_fromMatrix - создает новую матрицу преобразований

Аргументы:

- ``float a00, float a01, float a02`` - элементы (0,0), (0,1), (0,2)
- ``float a10, float a11, float a12`` - элементы (1,0), (1,1), (1,2)
- ``float a20, float a21, float a22`` - элементы (2,0), (2,1), (2,2)

**Возвращаемое значение:** ``sfTransform`` - матрица 3x3.

```c
CSFML_GRAPHICS_API sfTransform sfTransform_fromMatrix(float a00, float a01, float a02,
                                                      float a10, float a11, float a12,
                                                      float a20, float a21, float a22);
```
<hr/>

## sfTransform_getMatrix - получить матрицу 4x4

Эта функция заполняет матрицу 4x4 (массив из 16 чисел с плавающей запятой) с преобразованием из матрицы 3x3.

Матрица 4x4 напрямую совместима с функциями OpenGL.

Аргументы:

- ``const sfTransform* transform`` - матрица 3x3 (базовая)
- ``float* matrix`` - указатель на заранее подготовленный массив матрицы 4x4 (как ``float matrix[16];``)

```c
CSFML_GRAPHICS_API void sfTransform_getMatrix(const sfTransform* transform, float* matrix);
```

Пример:

```c
sfTransform transform = ...; // матрица 3x3 заданная где-то в коде
float matrix[16];
sfTransform_getMatrix(&transform, matrix)
glLoadMatrixf(matrix);
```

<hr/>

## sfTransform_getInverse - получить обратную трансформацию (инверсия)

Инвертирует матрицу, или вычисляет идентичное преобразование.

Аргументы:

- ``const sfTransform* transform`` - матрица 3x3 (базовая трансформация)

**Возвращаемое значение:** ``sfTransform`` - матрица 3x3 (результат инверсии).

```c
CSFML_GRAPHICS_API sfTransform sfTransform_getInverse(const sfTransform* transform);
```
<hr/>

## sfTransform_transformPoint - применить трансформацию к 2х мерной точке

Аргументы:

- ``const sfTransform* transform`` - матрица 3x3 (трансформация)
- ``sfVector2f point`` - точка

**Возвращаемое значение:** ``sfVector2f`` - результат трансформации.


```c
CSFML_GRAPHICS_API sfVector2f sfTransform_transformPoint(const sfTransform* transform, sfVector2f point);
```
<hr/>

## применить трансформацию к прямоугольной области

Если применяется поворот, область будет расширена до ограничивающего прямоугольника.

(фигуры работают немного по другому, но перобразование то-же)

Аргументы:

- ``const sfTransform* transform`` - матрица 3x3 (трансформация)
- ``sfFloatRect rectangle`` - область

**Возвращаемое значение:** ``sfFloatRect`` - результат трансформации.

```c
CSFML_GRAPHICS_API sfFloatRect sfTransform_transformRect(const sfTransform* transform, sfFloatRect rectangle);
```
<hr/>

## sfTransform_combine комбинирование трансформаций 

Перемножение матриц 

Аргументы:

- ``sfTransform* transform`` - первая матрица 3x3 (трансформация) - это преобразуемый объект, то есть в него получим изменения
- ``const sfTransform* other`` - вторая матрица 3x3 (трансформация2) - матрица для перемножения

```c
CSFML_GRAPHICS_API void sfTransform_combine(sfTransform* transform, const sfTransform* other);
```
<hr/>

## sfTransform_translate - перемещение

Аргументы:

- ``sfTransform* transform`` - матрица 3x3 - это преобразуемый объект, то есть в него получим изменения
- ``float x`` - перемещение по оси x
- ``float y`` - перемещение по оси y

```c
CSFML_GRAPHICS_API void sfTransform_translate(sfTransform* transform, float x, float y);
```
<hr/>

## sfTransform_rotate - поворот

Аргументы:

- ``sfTransform* transform`` - матрица 3x3 - это преобразуемый объект, то есть в него получим изменения
- ``float angle`` - угол в градусах

```c
CSFML_GRAPHICS_API void sfTransform_rotate(sfTransform* transform, float angle);
```
<hr/>

## sfTransform_rotateWithCenter - поворот с указанным центром

Центр поворота задается в координатах x и y. Позволяет совершать поворот вокруг указанных точек.

Аргументы:

- ``sfTransform* transform`` - матрица 3x3 - это преобразуемый объект, то есть в него получим изменения
- ``float angle`` - угол в градусах
- ``float centerX`` - координата x
- ``float centerY`` - координата y

```c
CSFML_GRAPHICS_API void sfTransform_rotateWithCenter(sfTransform* transform, float angle, float centerX, float centerY);
```
<hr/>

## sfTransform_scale - масштабирование

Аргументы:

- ``sfTransform* transform`` - матрица 3x3 - это преобразуемый объект, то есть в него получим изменения
- ``float scaleX`` - масштаб по оси x
- ``float scaleY`` - масштаб по оси y

```c
CSFML_GRAPHICS_API void sfTransform_scale(sfTransform* transform, float scaleX, float scaleY);
```
<hr/>

## sfTransform_scaleWithCenter масштабирование с указанным центром

Позволяет масштабировать от указанной точки

Аргументы:

- ``sfTransform* transform`` - матрица 3x3 - это преобразуемый объект, то есть в него получим изменения
- ``float scaleX`` - масштаб по оси x
- ``float scaleY`` - масштаб по оси y
- ``float centerX`` - координата центра по оси x
- ``float centerY`` - координата центра по оси y

```c
CSFML_GRAPHICS_API void sfTransform_scaleWithCenter(sfTransform* transform, float scaleX, float scaleY, float centerX, float centerY);
```
<hr/>

## sfTransform_equal - проверка идентичности преобразований

Аргументы:

- ``sfTransform* left`` - первая матрица 3x3
- ``sfTransform* right`` - вторая матрица 3x3

**Возвращаемое значение:** ``sfBool`` - результат (sfTrue - равны; sfFalse - не равны).

```c
CSFML_GRAPHICS_API sfBool sfTransform_equal(sfTransform* left, sfTransform* right);
```
<hr/>

```c
#endif // SFML_TRANSFORM_H
```
<hr/>

