# Sleep.h - пауза

```#include <SFML/System/Sleep.h>```

<hr/>

```c
#ifndef SFML_SLEEP_H
#define SFML_SLEEP_H

////////////////////////////////////////////////////////////
// Headers
////////////////////////////////////////////////////////////
#include <SFML/System/Export.h>
#include <SFML/System/Time.h>
```
<hr/>

## sfSleep - пауза

Остановить текущий процесс на временной интервал.

Это удобная функция для организации паузы в программе, так как она не блокирует работу компьютера забирая ресурсы центрального процессора.

Аргументы:
- **sfTime duration** - время остановки

```c
CSFML_SYSTEM_API void sfSleep(sfTime duration);
```
<hr/>


```c
#endif // SFML_SLEEP_H
```
