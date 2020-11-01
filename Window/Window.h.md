# Window.h - описание окна

```#include <SFML/Window/Window.h>```
<hr/>

```c
#ifndef SFML_WINDOW_H
#define SFML_WINDOW_H

////////////////////////////////////////////////////////////
// Headers
////////////////////////////////////////////////////////////
#include <SFML/Window/Export.h>
#include <SFML/Window/Event.h>
#include <SFML/Window/VideoMode.h>
#include <SFML/Window/WindowHandle.h>
#include <SFML/Window/Types.h>
#include <SFML/System/Vector2.h>
```
<hr/>

## sfWindowStyle - стили окна

Перечисление стилей для окна.

```c
typedef enum
{
    sfNone         = 0,      ///< Без рамки (без заголовка)
    sfTitlebar     = 1 << 0, ///< Заголовок + фиксированный размер + рамка
    sfResize       = 1 << 1, ///< Заголовок + изменяемый размер + рамка + кнопка maximize
    sfClose        = 1 << 2, ///< Заголовок + кнопка close
    sfFullscreen   = 1 << 3, ///< Полноэкранный режим
    sfDefaultStyle = sfTitlebar | sfResize | sfClose ///< Стиль по умолчанию
} sfWindowStyle;
```
<hr/>

## sfContextAttribute - флаги контекста

Перечисление флагов контекста окна.

```c
typedef enum
{
    sfContextDefault = 0,      ///< Без отладки, контекст совместимости (исключает последующие флаги)
    sfContextCore    = 1 << 0, ///< Атрибуты ядра 
    sfContextDebug   = 1 << 2  ///< Отладка
} sfContextAttribute;
```
<hr/>

## sfContextSettings - описание контекста окна 

Структура, описывающая параметры создаваемого окна.

```c
typedef struct
{
    unsigned int depthBits;         ///< Битность буфера глубины цвета
    unsigned int stencilBits;       ///< Битность буфера трафарета
    unsigned int antialiasingLevel; ///< Уровень сглаживания
    unsigned int majorVersion;      ///< Мажорная версия контекста OpenGL
    unsigned int minorVersion;      ///< Минорная версия контекста OpenGL
    sfUint32     attributeFlags;    ///< Флаги контекста
    sfBool       sRgbCapable;       ///< Описывается ли буфер цвета по типу RGB (использование цветов RGB)
} sfContextSettings;
```
<hr/>

## sfWindow_create - конструктор окна UTF-8

Создает новое окно и возвращает на него указатель.

Аргументы:

- ``sfVideoMode mode`` - режим окна (см VideoMode.h)
- ``const char* title`` - заголовок окна в кодировке UTF-8
- ``sfUint32 style`` - стили окна (см sfWindowStyle)
- ``const sfContextSettings* settings`` - установки контекста окна (см sfContextAttribute)

``Возвращаемое значение: sfWindow*`` - ссылка на созданное окно

```c
CSFML_WINDOW_API sfWindow* sfWindow_create(
                                    sfVideoMode mode, 
                                    const char* title, 
                                    sfUint32 style, 
                                    const sfContextSettings* settings
                                    );
```
<hr/>

## sfWindow_createUnicode - конструктор окна UTF-32

Создает новое окно и возвращает на него указатель.

Аргументы:

- ``sfVideoMode mode`` - режим окна (см - VideoMode.h])
- ``const char* title`` - заголовок окна в кодировке UTF-32
- ``sfUint32 style`` - стили окна (см sfWindowStyle)
- ``const sfContextSettings* settings`` - установки контекста окна (см sfContextAttribute)

``Возвращаемое значение: sfWindow*`` - ссылка на созданное окно

```c
CSFML_WINDOW_API sfWindow* sfWindow_createUnicode(
                                    sfVideoMode mode, 
                                    const sfUint32* title, 
                                    sfUint32 style, 
                                    const sfContextSettings* settings
                                    );
```
<hr/>

## sfWindow_createFromHandle - конструктор по элементу управления

Создание окна из существующего элемента управления.

Используйте этот конструктор, если хотите создать область рендеринга OpenGL в уже существующем элементе управления.

Аргументы:

- ``sfWindowHandle handle`` - элемент управления, из которого необходимо создать окно
- ``const sfContextSettings* settings`` - расширенные параметры OpenGL

``Возвращаемое значение: sfWindow*`` - ссылка на созданное окно

```c
CSFML_WINDOW_API sfWindow* sfWindow_createFromHandle(sfWindowHandle handle, const sfContextSettings* settings);
```
<hr/>

## sfWindow_destroy - удалить окно

Удалить окно из памяти.

Аргументы:

-  ``sfWindow*`` - удаляемое окно

**Возвращаемое значение:** ``void``

```c
CSFML_WINDOW_API void sfWindow_destroy(sfWindow* window);
```
<hr/>

## sfWindow_close - закрыть окно

Закрывает окно (удаляет вложенные ресурсы).

После вызова этой функции объект окна sfWindow остается в памяти, вы должны вызвать sfWindow_destroy, чтобы фактически удалить его. 

Все остальные функции, такие как sfWindow_pollEvent или sfWindow_display, по-прежнему будут работать (т. е. вам не нужно каждый раз тестировать sfWindow_isOpen) но не будут иметь никакого влияния на закрытые окна.

Аргументы:

- ``sfWindow* window `` - закрываемое окно

**Возвращаемое значение:** ``void``

```c
CSFML_WINDOW_API void sfWindow_close(sfWindow* window);
```
<hr/>

## sfWindow_isOpen - проверить существует ли окно

Проверяет существует ли окно. Закрытое, но не удаленное окно вернет true.

Аргументы:

- ``const sfWindow* window`` - проверяемое окно

``Возвращаемое значение:sfBool`` - sfTrue - если окно существует.

```c
CSFML_WINDOW_API sfBool sfWindow_isOpen(const sfWindow* window);
```
<hr/>

## sfWindow_getSettings - получить контекст окна 

Получить текущий контекст настроек окна для работы с OpenGL.

Аргументы:

- ``void`` - отсутствуют

**Возвращаемое значение:** ``sfContextSettings`` - структура настроек контекста окна

```c
CSFML_WINDOW_API sfContextSettings sfWindow_getSettings(const sfWindow* window);
```
<hr/>

## sfWindow_pollEvent - получить событие окна

Получает событие окна из вершины очереди событий для его обработки. Вершина очереди очищается.

Обратите внимание, что в очереди может присутствовать несколько событий, поэтому лучше вызывать эту функцию в цикле, чтобы убедиться, что вы обрабатываете каждое ожидающее событие.

(см. Event.h - события)

Аргументы:

- ``sfWindow* window`` - окно, для которого проверяются события
- ``sfEvent* event`` - ссылка на структуру описывающую события (в неё будет возвращено событие из очереди)

**Возвращаемое значение:** ``sfBool`` - sfTrue событие получено; sfFalse - события в очереди отсутствуют.

```c
CSFML_WINDOW_API sfBool sfWindow_pollEvent(sfWindow* window, sfEvent* event);
```
<hr/>

## sfWindow_waitEvent - ждать событие

Блокирует поток и ждет событие. Используется, если необходимо заблокировать выполнение программы до ожидания события.

(см. Event.h - события)

Аргументы:

- ``sfWindow* window`` - окно, для которого проверяются события
- ``sfEvent* event`` - ссылка на структуру описывающую события (в неё будет возвращено событие из очереди)

**Возвращаемое значение:** ``sfBool`` - sfTrue событие получено; sfFalse - события в очереди отсутствуют (всегда sfTrue).

```c
CSFML_WINDOW_API sfBool sfWindow_waitEvent(sfWindow* window, sfEvent* event);
```
<hr/>

## sfWindow_getPosition - получить позицию окна 

Получить позицию окна на экране.

Аргументы:

- ``const sfWindow* window`` - ссылка на окно

**Возвращаемое значение:** ``sfVector2i`` - позиция окна (см Vector2.h - описание двумерного вектора)

```c
CSFML_WINDOW_API sfVector2i sfWindow_getPosition(const sfWindow* window);
```
<hr/>

## sfWindow_setPosition - установить позицию окна

Установить позицию окна на экране.

Аргументы:

- ``sfWindow* window`` - ссылка на окно
- ``sfVector2i position`` - новая позиция (см [[сsfml:сsfml-System.Vector2|Vector2.h - описание двумерного вектора]])


**Возвращаемое значение:** ``void``

```c
CSFML_WINDOW_API void sfWindow_setPosition(sfWindow* window, sfVector2i position);
```
<hr/>

## sfWindow_getSize - получить размер окна

Получить размер окна.

Аргументы:

- ``const sfWindow* window`` - ссылка на окно

**Возвращаемое значение:** ``sfVector2u`` - размер окна (см Vector2.h - описание двумерного вектора)

```c
CSFML_WINDOW_API sfVector2u sfWindow_getSize(const sfWindow* window);
```
<hr/>

## sfWindow_setSize - установить размер окна

Установитьразмер окна.

Аргументы:

- ``const sfWindow* window`` - ссылка на окно
- ``sfVector2u size`` - новый размер окна (см Vector2.h - описание двумерного вектора)

**Возвращаемое значение:** ``void``

```c
CSFML_WINDOW_API void sfWindow_setSize(sfWindow* window, sfVector2u size);
```
<hr/>

## sfWindow_setTitle - установить заголовок окна в UTF-8

Установить заголовок окна в кодировке UTF-8.

Аргументы:

- ``sfWindow* window`` - ссылка на окно
- ``const char* title`` - заголовок

**Возвращаемое значение:** ``void``

```c
CSFML_WINDOW_API void sfWindow_setTitle(sfWindow* window, const char* title);
```
<hr/>

## sfWindow_setUnicodeTitle - установить заголовок окна в UTF-32

Установить заголовок окна в кодировке UTF-32.

Аргументы:

- ``sfWindow* window`` - ссылка на окно
- ``const char* title`` - заголовок

**Возвращаемое значение:** ``void``

```c
CSFML_WINDOW_API void sfWindow_setUnicodeTitle(sfWindow* window, const sfUint32* title);
```
<hr/>

## sfWindow_setIcon - установить иконку окна 

Установить иконку окна. 

Иконка должна храниться двумерным массивом в памяти в формате RGBA-32 - это 32 бита на цветовой компонент и 32+32+32+32=128 бит на пиксель (16 байт на 1 пискель).

Аргументы:

- ``sfWindow* window`` - ссылка на окно
- ``unsigned int width`` - ширина иконки в пикселах
- ``unsigned int height`` - высота иконки в пикселах
- ``const sfUint8* pixels`` - ссылка на иконку в памяти

**Возвращаемое значение:** ``void``

```c
CSFML_WINDOW_API void sfWindow_setIcon(sfWindow* window, unsigned int width, unsigned int height, const sfUint8* pixels);
```
<hr/>

## sfWindow_setVisible - показать/скрыть окно

Показать или скрыть окно.

Аргументы:

- ``sfWindow* window`` - ссылка на окно
- ``sfBool visible`` - отображение (sfTrue - показать; sfFalse - скрыть)

**Возвращаемое значение:** ``void``

```c
CSFML_WINDOW_API void sfWindow_setVisible(sfWindow* window, sfBool visible);
```
<hr/>

## sfWindow_setVerticalSyncEnabled - вертикальная синхронизация

Вертикальная синхронизация окна (v-sync).

Позволяет ограничить частоту кадров и избежать "артефактов" при прорисовке кадра. 

Аргументы:

- ``sfWindow* window`` - ссылка на окно
- ``sfBool enabled`` - включить/отключить синхронизацию (sfTrue - включить; sfFalse - отключить)

**Возвращаемое значение:** ``void``

```c
CSFML_WINDOW_API void sfWindow_setVerticalSyncEnabled(sfWindow* window, sfBool enabled);
```
<hr/>

## sfWindow_setMouseCursorVisible - показать/скрыть курсор мышки

Показать или скрыть курсор мышки.

Аргументы:

- ``sfWindow* window`` - ссылка на окно
- ``sfBool visible`` - отображение (sfTrue - показать; sfFalse - скрыть)

**Возвращаемое значение:** ``void``

```c
CSFML_WINDOW_API void sfWindow_setMouseCursorVisible(sfWindow* window, sfBool visible);
```
<hr/>

## sfWindow_setMouseCursorGrabbed - захват курсора мышки

Захваченный курсор не может выйти за пределы окна. Обратите внимание, что захват активен только тогда, когда окно имеет фокус, и вызов этой функции для полноэкранных окон не будет иметь никакого эффекта (полноэкранные окна всегда захватывают курсор).

Аргументы:

- ``sfWindow* window`` - ссылка на окно
- ``sfBool grabbed``захват (sfTrue - захватить; sfFalse - отпустить)

**Возвращаемое значение:** ``void``

```c
CSFML_WINDOW_API void sfWindow_setMouseCursorGrabbed(sfWindow* window, sfBool grabbed);
```
<hr/>

## sfWindow_setMouseCursor - установить системный курсор мышки

Установить системный курсор мышки.

При создании окна по умолчанию используется Курсор со стрелкой.

Курсор нельзя уничтожать во время работы окна.

Функции, связанные с курсором, не поддерживаются на iOS и Android.

Аргументы:

- ``sfWindow* window`` - ссылка на окно
- ``const sfCursor* cursor`` - курсор 

**Возвращаемое значение:** ``void``

Дополнительно смотрите: Cursor.h)
- sfCursor_createFromSystem
- sfCursor_createFromPixels


```c
CSFML_WINDOW_API void sfWindow_setMouseCursor(sfWindow* window, const sfCursor* cursor);
```
<hr/>

## sfWindow_setKeyRepeatEnabled - автоповтор клавиш

Включить/выключить автоповтор клавиш.

Если функция key repeat включена, окно будет получать повторяющиеся события при удержании клавиши в нажатом состоянии. Если он отключен, окно получит только одно событие нажатой клавиши.

По умолчанию автоповтор включен.

Аргументы:

- ``sfWindow* window`` - ссылка на окно
- ``sfBool enabled`` -  (sfTrue - включить; sfFalse - отключить)

**Возвращаемое значение:** ``void``

```c
CSFML_WINDOW_API void sfWindow_setKeyRepeatEnabled(sfWindow* window, sfBool enabled);
```
<hr/>

## sfWindow_setFramerateLimit - ограничить частоту кадров

Ограничить частоту кадров.

Если задано ограничение, окно будет использовать небольшую задержку после каждого вызова sfWindow_display, чтобы гарантировать частоту кадров и выдержать время задержки отдельного кадра.

Аргументы:

- ``sfWindow* window`` - ссылка на окно
- ``unsigned int limit`` - частота кадров

**Возвращаемое значение:** ``void``

```c
CSFML_WINDOW_API void sfWindow_setFramerateLimit(sfWindow* window, unsigned int limit);
```
<hr/>

## sfWindow_setJoystickThreshold - задать порог чувствительности джойстика

Задать порог чувствительности джойстика.

Порог чувствительности  джойстика - это значение, ниже которого не будет генерироваться событие JoyMoved.

Аргументы:

- ``sfWindow* window`` - ссылка на окно
- ``float threshold`` - порог чувствительности в диапазоне [0, 100]

**Возвращаемое значение:** ``void``

```c
CSFML_WINDOW_API void sfWindow_setJoystickThreshold(sfWindow* window, float threshold);
```
<hr/>

## sfWindow_setActive - активация/деактивация окна

Активировать/деактивировать окно.

Точный перевод: Активация или деактивация окна в качестве текущей цели для рендеринга OpenGL.

Одновременно в потоке может быть активировано только одно окно, поэтому ранее активное окно (если таковое имеется) автоматически деактивируется. Не следует путать с sfWindow_requestFocus().

Аргументы:

- ``sfWindow* window`` - ссылка на окно
- ``sfBool active`` - (sfTrue - активировать; sfFalse - деактивировать)

**Возвращаемое значение:** ``sfBool`` - результат действия (sfTrue - удачно; sfFalse - неудачно)

```c
CSFML_WINDOW_API sfBool sfWindow_setActive(sfWindow* window, sfBool active);
```
<hr/>

## sfWindow_requestFocus - активация фокуса ввода

Запросить активацию окна с отображением его на переднем плане.

Только одно окно может иметь фокус ввода в один промежуток времени. 

Эта функция, запрашивает у операционной системы фокусировку ввода в окно. Операционная система может отклонить запрос (допустим из за занятости окна тяжелым процессом). 

Не следует путать с sfWindow_setActive().

Аргументы:

- ``const sfWindow* window`` - ссылка на окно

**Возвращаемое значение:** ``void``

```c
CSFML_WINDOW_API void sfWindow_requestFocus(sfWindow* window);
```
<hr/>

## sfWindow_hasFocus - проверить фокус ввода

Проверить, имеет ли окно фокус ввода.

Аргументы:

- ``const sfWindow* window`` - ссылка на окно

**Возвращаемое значение:** ``sfBool`` - значение фокуса ввода для окна (sfTrue - имеет фокус ввода; sfFalse - не имеет фокус ввода)

```c
CSFML_WINDOW_API sfBool sfWindow_hasFocus(const sfWindow* window);
```
<hr/>

## sfWindow_display - отрисовка буфера в окне

Функция отображает кадр в окне после его прорисовки (двойная буферизация).

Аргументы:

- ``sfWindow* window`` - ссылка на окно

**Возвращаемое значение:** ``void``

```c
CSFML_WINDOW_API void sfWindow_display(sfWindow* window);
```
<hr/>

## sfWindow_getSystemHandle - получить дескриптор окна

Получить дескриптор окна специфичный для рабочей операционной системы.

Аргументы:

- ``const sfWindow* window`` - ссылка на окно

**Возвращаемое значение:** ``sfWindowHandle`` - дескриптор окна (см. WindowHandle.h)

```c
CSFML_WINDOW_API sfWindowHandle sfWindow_getSystemHandle(const sfWindow* window);
```
<hr/>


```c
#endif // SFML_WINDOW_H
```
<hr/>



