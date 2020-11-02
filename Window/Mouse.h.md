# Mouse.h - события мышки

```#include <SFML/Window/Mouse.h>```
<hr/>


```c
#ifndef SFML_MOUSE_H
#define SFML_MOUSE_H

////////////////////////////////////////////////////////////
// Headers
////////////////////////////////////////////////////////////
#include <SFML/Window/Export.h>
#include <SFML/Window/Types.h>
#include <SFML/System/Vector2.h>
```
<hr/>

## sfMouseButton - перечисление для кнопок мышки

Перечисление для кнопок мышки.

```c
typedef enum
{
    sfMouseLeft,       ///< левая кнопка мышки
    sfMouseRight,      ///< правая кнопка мышки
    sfMouseMiddle,     ///< средняя кнопка мышки (колесико)
    sfMouseXButton1,   ///< кнопка мышки "предыдущий выбор" (игровая мышка)
    sfMouseXButton2,   ///< кнопка мышки "следующий выбор" (игровая мышка)

    sfMouseButtonCount ///< Keep last -- общее количество кнопок мыши
} sfMouseButton;
```
<hr/>

## sfMouseWheel - перечисление для колес мышки

Перечисление для колес мышки.

```c
typedef enum
{
    sfMouseVerticalWheel,  ///< вертикальное колесо
    sfMouseHorizontalWheel ///< горизонтальное колесо (игровая мышка)
} sfMouseWheel;

```
<hr/>

## sfMouse_isButtonPressed - проверка нажатия клавиши мышки

Проверка нажатия клавиши мышки.

Аргументы:

- ``sfMouseButton button`` - описание проверяемой кнопки

**Возвращаемое значение:** ``sfBool`` - sfTrue - кнопка нажата; sfFalse - кнопка не нажата

```c
CSFML_WINDOW_API sfBool sfMouse_isButtonPressed(sfMouseButton button);
```
<hr/>

## sfMouse_getPosition - получить текущую позицию мышки ======

Функция возвращает текущее положение курсора мыши относительно данного окна или рабочего стола, если передано значение NULL.

Аргументы:

- ``const sfWindow* relativeTo`` - ссылка на окно

**Возвращаемое значение:** ``sfVector2i`` - вектор координат

```c
CSFML_WINDOW_API sfVector2i sfMouse_getPosition(const sfWindow* relativeTo);
```
<hr/>

## sfMouse_setPosition - Установить текущую позицию мышки ======

Функция устанавливает текущее положение курсора мыши относительно данного окна или рабочего стола, если передается значение NULL.

Аргументы:

- ``sfVector2i position`` - вектор позиции
- ``const sfWindow* relativeTo`` - ссылка на окно или NULL

**Возвращаемое значение:** ``void``

```c
CSFML_WINDOW_API void sfMouse_setPosition(sfVector2i position, const sfWindow* relativeTo);
```
<hr/>


```c
#endif // SFML_MOUSE_H
```
<hr/>
