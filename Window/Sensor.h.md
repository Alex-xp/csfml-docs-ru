# Sensor.h - события датчика сенсора

```#include <SFML/Window/Sensor.h>```

(сенсора у меня нет - в действии не проверено)

<hr/>


```c
#ifndef SFML_SENSOR_H
#define SFML_SENSOR_H

////////////////////////////////////////////////////////////
// Headers
////////////////////////////////////////////////////////////
#include <SFML/Window/Export.h>
#include <SFML/Window/Types.h>
#include <SFML/System/Vector3.h>
```
<hr/>

## sfSensorType - структура описания типов датчиков сенсора


```c
typedef enum
{
    sfSensorAccelerometer,    ///< Измеряет исходное ускорение (m/s^2)
    sfSensorGyroscope,        ///< Измеряет исходную скорость вращения (degrees/s)
    sfSensorMagnetometer,     ///< Измеряет окружающее магнитное поле (micro-teslas)
    sfSensorGravity,          ///< Измеряет направление и силу тяжести независимо от ускорения устройства. (m/s^2)
    sfSensorUserAcceleration, ///< Измеряет направление и интенсивность ускорения устройства независимо от силы тяжести. (m/s^2)
    sfSensorOrientation,      ///< Measures the absolute 3D orientation (degrees)

    sfSensorCount             ///< Keep last -- общее количество типов датчиков
} sfSensorType;
```
<hr/>

## sfSensor_isAvailable - доступен ли датчик на базовой платформе

Аргументы:

- ``sfSensorType sensor`` - тип проверяемого датчика

**Возвращаемое значение:** ``sfBool`` - результат (sfTrue - доступен; sfFalse - не доступен)

```c
CSFML_WINDOW_API sfBool sfSensor_isAvailable(sfSensorType sensor);
```
<hr/>

## sfSensor_setEnabled - включить/выключить датчик

Все датчики по умолчанию отключены, чтобы не расходовать слишком много энергии батареи. 
Как только датчик будет включен, он начинет отправлять события соответствующего типа.

Аргументы:

- ``sfSensorType sensor`` - тип датчика
- ``sfBool enabled`` - включение (sfTrue - включить; sfFalse - отключить)

**Возвращаемое значение:** ``void``

```c
CSFML_WINDOW_API void sfSensor_setEnabled(sfSensorType sensor, sfBool enabled);
```
<hr/>

## sfSensor_getValue - получить значение сенсора

Аргументы:

- ``sfSensorType sensor`` - тип датчика

**Возвращаемое значение:** ``sfVector3f`` - значение с датчика сенсора

```c
CSFML_WINDOW_API sfVector3f sfSensor_getValue(sfSensorType sensor);
```
<hr/>


```c
#endif // SFML_SENSOR_H

```
<hr/>



