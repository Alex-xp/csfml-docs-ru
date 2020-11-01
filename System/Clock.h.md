# Clock.h - объект управления временем (часы)

``#include <SFML/System/Clock.h>``

<hr/>

```c
#ifndef SFML_CLOCK_H
#define SFML_CLOCK_H

////////////////////////////////////////////////////////////
// Headers
////////////////////////////////////////////////////////////
#include <SFML/System/Export.h>
#include <SFML/System/Time.h>
#include <SFML/System/Types.h>

```

<hr/>

## sfClock_create - создать объект подсчета времени

Вернет ссылку на объект типа: sfClock.

```c
CSFML_SYSTEM_API sfClock* sfClock_create(void);
```

<hr/>

## sfClock_copy - создать объект подсчета времени копированием

Вернет ссылку на объект типа: sfClock.

```c
CSFML_SYSTEM_API sfClock* sfClock_copy(const sfClock* clock);
```

<hr/>

## sfClock_destroy - удалить объект подсчета времени

Аргументы:
- ** sfClock* clock ** - объект подсчета времени

```c
CSFML_SYSTEM_API void sfClock_destroy(sfClock* clock);
```

<hr/>

## sfClock_getElapsedTime - получить время

Эта функция возвращает время, прошедшее с момента последнего вызова sfClock_restart (или время создания объекта sfClock, если sfClock_restart не был вызван).

Аргументы:
- ** sfClock* clock ** - объект подсчета времени

Вернет объект типа sfTime

```c
CSFML_SYSTEM_API sfTime sfClock_getElapsedTime(const sfClock* clock);
```

<hr/>

## sfClock_restart - перезапустить подсчет времени

Эта функция сбрасывает счетчик времени. Он также возвращает время, прошедшее с момента запуска часов.

Аргументы:
- ** sfClock* clock ** - объект подсчета времени

Вернет объект типа sfTime

```c
CSFML_SYSTEM_API sfTime sfClock_restart(sfClock* clock);
```

<hr/>


```c
#endif // SFML_CLOCK_H
```











