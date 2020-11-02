# Event.h - РАБОТА С СОБЫТИЯМИ

```#include <SFML/Window/Event.h>```
<hr/>




```c
#ifndef SFML_EVENT_H
#define SFML_EVENT_H

////////////////////////////////////////////////////////////
// Headers
////////////////////////////////////////////////////////////
#include <SFML/Window/Export.h>
#include <SFML/Window/Joystick.h>
#include <SFML/Window/Keyboard.h>
#include <SFML/Window/Mouse.h>
#include <SFML/Window/Sensor.h>
```
<hr/>

## sfEventType - типы событий 

Структура, описывающая типы возможных событий.

```c
typedef enum
{
    sfEvtClosed,                 ///< Запрос закрытия окна (без данных)
    sfEvtResized,                ///< Изменен размер окна (данные в: event.size)
    sfEvtLostFocus,              ///< Окно потеряло фокус (без данных)
    sfEvtGainedFocus,            ///< Окно получило фокус (без данных)
    sfEvtTextEntered,            ///< Был введен символ (данные в: event.text)
    sfEvtKeyPressed,             ///< Была нажата клавиша (данные в: event.key)
    sfEvtKeyReleased,            ///< Была отпущена клавиша (данные в: event.key)
    sfEvtMouseWheelMoved,        ///< Было прокручено колесико мышки (данные в: event.mouseWheel) (УСТАРЕЛО)
    sfEvtMouseWheelScrolled,     ///< Было прокручено колесико мышки (данные в: event.mouseWheelScroll)
    sfEvtMouseButtonPressed,     ///< Была нажата кнопка мышки (данные в: event.mouseButton)
    sfEvtMouseButtonReleased,    ///< Была отпущена кнопка мышки (данные в: event.mouseButton)
    sfEvtMouseMoved,             ///< Перемещение курсора мышки (данные в: event.mouseMove)
    sfEvtMouseEntered,           ///< Курсор мышки вошел в область окна (без данных)
    sfEvtMouseLeft,              ///< Курсор мышки вышел из области окна (без данных)
    sfEvtJoystickButtonPressed,  ///< Была нажата кнопка на джойстике (данные в: event.joystickButton)
    sfEvtJoystickButtonReleased, ///< Была отпущена кнопка на джойстике (данные в: event.joystickButton)
    sfEvtJoystickMoved,          ///< Перемещение джойстика вдоль оси (данные в: event.joystickMove)
    sfEvtJoystickConnected,      ///< Подключение джойстика (данные в: event.joystickConnect)
    sfEvtJoystickDisconnected,   ///< Отключение джойстика (данные в: event.joystickConnect)
    sfEvtTouchBegan,             ///< Начало событий сенсора (данные в: event.touch)
    sfEvtTouchMoved,             ///< Прикосновение с перемещением (данные в: event.touch)
    sfEvtTouchEnded,             ///< Конец событий сенсора (данные в: event.touch)
    sfEvtSensorChanged,          ///< Изменение показаний датчика сенсора (данные в: event.sensor)

    sfEvtCount,                  ///< Keep last -- Общее количество событий
} sfEventType;
```
<hr/>

## sfKeyEvent - события клавиатуры

Структура с описанием событий клавиатуры.

```c
typedef struct
{
    sfEventType type;     //< тип события
    sfKeyCode   code;     //< код клавиши
    sfBool      alt;      //< зажата клавиша Alt
    sfBool      control;  //< зажата клавиша Ctrl
    sfBool      shift;    //< зажата клавиша Shift
    sfBool      system;   //< зажата клавиша System
} sfKeyEvent;
```
<hr/>

## sfTextEvent - текстовые события

Структура описания текстовых событий.

```c
typedef struct
{
    sfEventType type;
    sfUint32    unicode;
} sfTextEvent;
```
<hr/>

## sfMouseMoveEvent - события мышки

Структура описаний событий мышки.

```c
typedef struct
{
    sfEventType type; //< тип события
    int         x;    //< положение курсора по оси x
    int         y;    //< положение курсора по оси y
} sfMouseMoveEvent;
```
<hr/>

## sfMouseButtonEvent - события кнопок мышки

Структура описания событий кнопок мышки.

```c
typedef struct
{
    sfEventType   type;    //< тип события
    sfMouseButton button;  //< номер кнопки из перечисления sfMouseButton 
    int           x;       //< положение курсора по оси x
    int           y;       //< положение курсора по оси y
} sfMouseButtonEvent;
```
<hr/>

## sfMouseButtonEvent - события колесика мышки (уст)

Структура описания событий колесика мышки.

(УСТАРЕЛО - необходимо использовать sfMouseWheelScrollEvent)

```c
typedef struct CSFML_DEPRECATED
{
    sfEventType type;   //< тип события
    int         delta;  //< величина прокрутки колесика
    int         x;      //< положение курсора по оси x
    int         y;      //< положение курсора по оси y
} sfMouseWheelEvent;
```
<hr/>

## sfMouseWheelScrollEvent - события колесика мышки

Структура описания событий колесика мышки.

(дополнительно смотреть: Mouse.h)

```c
typedef struct
{
    sfEventType  type;      //< тип события
    sfMouseWheel wheel;     //< структура описания смещения колесика
    float        delta;     //< величина прокрутки колесика
    int          x;         //< положение курсора по оси x
    int          y;         //< положение курсора по оси y
} sfMouseWheelScrollEvent;
```
<hr/>

## sfJoystickMoveEvent - события перемещения джойстика вдоль оси

События перемещения джойстика вдоль оси.

```c
typedef struct
{
    sfEventType    type;         //< тип события
    unsigned int   joystickId;
    sfJoystickAxis axis;
    float          position;
} sfJoystickMoveEvent;
```
<hr/>

## sfJoystickButtonEvent - события кнопок джойстика

Структура описания событий кнопок джойстика.

```c
typedef struct
{
    sfEventType  type;
    unsigned int joystickId;
    unsigned int button;
} sfJoystickButtonEvent;
```
<hr/>

## sfJoystickConnectEvent - события подключения/отключения джойстика

Структура описаний событий подключения/отключения джойстика.

```c
typedef struct
{
    sfEventType  type;
    unsigned int joystickId;
} sfJoystickConnectEvent;
```
<hr/>

## sfSizeEvent - события изменения размеров

Структура описания событий изменения размеров.

```c
typedef struct
{
    sfEventType  type;    //< тип события
    unsigned int width;   //< ширина
    unsigned int height;  //< высота
} sfSizeEvent;
```
<hr/>

## sfTouchEvent - события прикосновения

Структура описания событий прикосновения.

```c
typedef struct
{
    sfEventType  type;
    unsigned int finger;
    int          x;
    int          y;
} sfTouchEvent;
```
<hr/>

## sfSensorEvent - сенсорные события

Структура описания общих сенсорных событий.

```c
typedef struct
{
    sfEventType  type;
    sfSensorType sensorType;
    float        x;
    float        y;
    float        z;
} sfSensorEvent;
```
<hr/>

## sfEvent - СОБЫТИЯ

Обобщающее объединение описания системных и оконных параметров.

```c
typedef union
{
    sfEventType             type;             ///< тип события
    sfSizeEvent             size;             ///< размер параметров события
    sfKeyEvent              key;              ///< параметры событий клавиатуры
    sfTextEvent             text;             ///< параметры текстовых событий
    sfMouseMoveEvent        mouseMove;        ///< параметры событий мышки
    sfMouseButtonEvent      mouseButton;      ///< параметры событий кнопок мышки
    sfMouseWheelEvent       mouseWheel;       ///< параметры событий колесика мышки (УСТАРЕЛО)
    sfMouseWheelScrollEvent mouseWheelScroll; ///< параметры событий колесика мышки
    sfJoystickMoveEvent     joystickMove;     ///< параметры событий перемещения джойстика
    sfJoystickButtonEvent   joystickButton;   ///< параметры событий кнопок джойстика
    sfJoystickConnectEvent  joystickConnect;  ///< параметры событий подключения/отключения джойстика
    sfTouchEvent            touch;            ///< параметры событий прикосновения
    sfSensorEvent           sensor;           ///< параметры событий сенсора
} sfEvent;
</Code>
```
<hr/>


```c
#endif // SFML_EVENT_H
```
<hr/>

