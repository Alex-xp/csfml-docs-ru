# Vector2.h - описание двумерного вектора

```#include <SFML/System/Vector2.h>```
<hr/>

```c
#ifndef SFML_VECTOR2_H
#define SFML_VECTOR2_H

////////////////////////////////////////////////////////////
// Headers
////////////////////////////////////////////////////////////
#include <SFML/System/Export.h>
```
<hr/>

## sfVector2i - вектор целых чисел

```c
typedef struct
{
    int x;
    int y;
} sfVector2i;
```
<hr/>

## sfVector2u - вектор целых чисел без знака

```c
typedef struct
{
    unsigned int x;
    unsigned int y;
} sfVector2u;
```
<hr/>

## sfVector2f - вектор чисел с плавающей точкой

```c
typedef struct
{
    float x;
    float y;
} sfVector2f;
```
<hr/>



```c
#endif // SFML_VECTOR2_H
```
<hr/>
