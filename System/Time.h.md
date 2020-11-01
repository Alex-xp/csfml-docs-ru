# Time.h - Описание времени

```#include <SFML/System.Time.h>```

<hr/>

```c
#ifndef SFML_TIME_H
#define SFML_TIME_H

////////////////////////////////////////////////////////////
// Headers
////////////////////////////////////////////////////////////
#include <SFML/System/Export.h>
```

<hr/>

## sfTime - структура описания времени в системе

```c
typedef struct
{
    sfInt64 microseconds;
} sfTime;
```

<hr/>

## sfTime_Zero - нулевое время

```c
CSFML_SYSTEM_API sfTime sfTime_Zero;
```

<hr/>

## sfTime_asSeconds - получить время в секундах

```c
CSFML_SYSTEM_API float sfTime_asSeconds(sfTime time);
```

<hr/>


## sfTime_asMilliseconds - получить время в милисекундах

```c
CSFML_SYSTEM_API sfInt32 sfTime_asMilliseconds(sfTime time);
```

<hr/>


## sfTime_asMicroseconds - получить время в микросекундах

```c
CSFML_SYSTEM_API sfInt64 sfTime_asMicroseconds(sfTime time);
```

<hr/>


##  sfSeconds - время в секундах

Создает представление времени с начальной инициализацией в секундах.

```c
CSFML_SYSTEM_API sfTime sfSeconds(float amount);
```

<hr/>


## sfMilliseconds - время в милисекундах

Создает представление времени с начальной инициализацией в милисекундах .

```c
CSFML_SYSTEM_API sfTime sfMilliseconds(sfInt32 amount);
```

<hr/>


## sfMicroseconds - время в микросекундах

Создает представление времени с начальной инициализацией в микросекундах .

```c
CSFML_SYSTEM_API sfTime sfMicroseconds(sfInt64 amount);
```

<hr/>


```c
#endif // SFML_TIME_H
```
