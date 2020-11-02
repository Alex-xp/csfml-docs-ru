# Joystick.h - события джойстика

```#include <SFML/Window/Joystick.h>```
<hr/>



```c
#ifndef SFML_JOYSTICK_H
#define SFML_JOYSTICK_H

////////////////////////////////////////////////////////////
// Headers
////////////////////////////////////////////////////////////
#include <SFML/Window/Export.h>
#include <SFML/Window/JoystickIdentification.h>
```
<hr/>

## Перечисление системной совместимости

```c
enum
{
    sfJoystickCount       = 8,  ///< Максимальное количество поддерживаемых джойстиков
    sfJoystickButtonCount = 32, ///< Максимальное количество поддерживаемых кнопок
    sfJoystickAxisCount   = 8   ///< Максимальное количество поддерживаемых осей
};
```
<hr/>

## sfJoystickAxis - оси, поддерживаемые джойстиками SFML

```c
typedef enum
{
    sfJoystickX,    ///< The X axis
    sfJoystickY,    ///< The Y axis
    sfJoystickZ,    ///< The Z axis
    sfJoystickR,    ///< The R axis
    sfJoystickU,    ///< The U axis
    sfJoystickV,    ///< The V axis
    sfJoystickPovX, ///< The X axis of the point-of-view hat
    sfJoystickPovY  ///< The Y axis of the point-of-view hat
} sfJoystickAxis;
```
<hr/>

## sfJoystick_isConnected - проверка подключения джойстика

Аргументы:

- ``unsigned int joystick`` - индекс джойстика в системе

**Возвращаемое значение:** ``sfBool`` - sfTrue - подключен; sfFalse - не подключен

```c
CSFML_WINDOW_API sfBool sfJoystick_isConnected(unsigned int joystick);
```
<hr/>

## sfJoystick_getButtonCount - получить количество кнопок на джойстике

Если джойстик не подключен - вернет 0.

Аргументы:

- ``unsigned int joystick`` - индекс джойстика в системе

**Возвращаемое значение:** ``unsigned int`` - количество кнопок

```c
CSFML_WINDOW_API unsigned int sfJoystick_getButtonCount(unsigned int joystick);
```
<hr/>

## sfJoystick_hasAxis - проверить поддержку оси

Если джойстик не подключен - вернет sfFalse.

Аргументы:

- ``unsigned int joystick`` - индекс джойстика в системе
- ``sfJoystickAxis axis`` - ось

**Возвращаемое значение:** ``sfBool`` - sfTrue - поддерживает; sfFalse - не поддерживает

```c
CSFML_WINDOW_API sfBool sfJoystick_hasAxis(unsigned int joystick, sfJoystickAxis axis);
```
<hr/>

## sfJoystick_isButtonPressed - проверить нажатие кнопки джойстика

Если джойстик не подключен - вернет sfFalse.

Аргументы:

- ``unsigned int joystick`` - индекс джойстика в системе
- ``unsigned int button`` - индекс кнопки

**Возвращаемое значение:** ``sfBool`` - sfTrue - нажата; sfFalse - не нажата

```c
CSFML_WINDOW_API sfBool sfJoystick_isButtonPressed(unsigned int joystick, unsigned int button);
```
<hr/>

## sfJoystick_getAxisPosition - получить позицию по оси

Аргументы:

- ``unsigned int joystick`` - индекс джойстика в системе
- ``sfJoystickAxis axis`` - ось

**Возвращаемое значение:** ``float`` - позиция в диапазоне [-100 .. 100]

```c
CSFML_WINDOW_API float sfJoystick_getAxisPosition(unsigned int joystick, sfJoystickAxis axis);
```
<hr/>

## sfJoystick_getIdentification - получить информацию по джойстику

Аргументы:

- ``unsigned int joystick`` - индекс джойстика в системе

**Возвращаемое значение:** ``sfJoystickIdentification`` - информация о джойстике

```c
CSFML_WINDOW_API sfJoystickIdentification sfJoystick_getIdentification(unsigned int joystick);
```
<hr/>

## sfJoystick_update - обновить состояние всех джойстиков

Если вы работаете с окнами - SFML сам вызывает данную функцию и нет необходимости её вызывать специально.

НО ЕСТЬ ОДНО ИСКЛЮЧЕНИЕ: если вы работаете без окна - тогда эта функцию необходимо вызывать для обновления информации о состоянии джойстиков.

```c
CSFML_WINDOW_API void sfJoystick_update(void);
```
<hr/>

```c
#endif // SFML_JOYSTICK_H
```
<hr/>

