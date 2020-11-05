# Texture.h - работа с текстурой

```#include <SFML/Graphics/BlendMode.h>```

<hr/>

```c
#ifndef SFML_TEXTURE_H
#define SFML_TEXTURE_H

////////////////////////////////////////////////////////////
// Headers
////////////////////////////////////////////////////////////
#include <SFML/Graphics/Export.h>
#include <SFML/Graphics/Rect.h>
#include <SFML/Graphics/Types.h>
#include <SFML/Window/Types.h>
#include <SFML/System/InputStream.h>
#include <SFML/System/Vector2.h>
#include <stddef.h>
```
<hr/>

## sfTexture_create - создает новый объект текстуры

Аргументы:

- ``unsigned int width`` - ширина
- ``unsigned int height`` - высота

**Возвращаемое значение:** ``sfTexture*`` - указатель на текстуру (NULL - при неудаче)

```c
CSFML_GRAPHICS_API sfTexture* sfTexture_create(unsigned int width, unsigned int height);
```
<hr/>

## sfTexture_createFromFile - создать текстуру из файла изображения

Аргументы:

- ``const char* filename`` - путь и имя загружаемого файла
- ``const sfIntRect* area`` - область в файле или NULL для всего файла целиком

**Возвращаемое значение:** ``sfTexture*`` - указатель на текстуру (NULL - при неудаче)

```c
CSFML_GRAPHICS_API sfTexture* sfTexture_createFromFile(const char* filename, const sfIntRect* area);
```
<hr/>

## sfTexture_createFromMemory - создать текстуру из массива данных в памяти

Аргументы:

- ``const void* data`` - ссылка на массив пикселей в памяти
- ``size_t sizeInBytes`` - размер массива в байтах
- ``const sfIntRect* area`` - область в изображении или NULL для всего изображения целиком

**Возвращаемое значение:** ``sfTexture*`` - указатель на текстуру (NULL - при неудаче)


```c
CSFML_GRAPHICS_API sfTexture* sfTexture_createFromMemory(const void* data, size_t sizeInBytes, const sfIntRect* area);
```
<hr/>

## sfTexture_createFromStream - создать текстуру из произвольных поточных данных

Аргументы:

- ``sfInputStream* stream`` - ссылка на поток
- ``const sfIntRect* area`` - область в изображении или NULL для всего изображения целиком

**Возвращаемое значение:** ``sfTexture*`` - указатель на текстуру (NULL - при неудаче)

```c
CSFML_GRAPHICS_API sfTexture* sfTexture_createFromStream(sfInputStream* stream, const sfIntRect* area);
```
<hr/>

## sfTexture_createFromMemory - создать текстуру из изображения

Аргументы:

- ``const sfImage* image`` - ссылка на изображение в памяти
- ``const sfIntRect* area`` - область в изображении или NULL для всего изображения целиком

**Возвращаемое значение:** ``sfTexture*`` - указатель на текстуру (NULL - при неудаче)

```c
CSFML_GRAPHICS_API sfTexture* sfTexture_createFromImage(const sfImage* image, const sfIntRect* area);
```
<hr/>

## sfTexture_copy - копировать текстуру

Аргументы:

- ``const sfImage* image`` - копируемая текстура

**Возвращаемое значение:** ``sfTexture*`` - новая текстура

```c
CSFML_GRAPHICS_API sfTexture* sfTexture_copy(const sfTexture* texture);
```
<hr/>

## sfTexture_destroy - удалить текстуру

Аргументы:

- ``sfTexture* texture`` - удаляемая текстура

```c
CSFML_GRAPHICS_API void sfTexture_destroy(sfTexture* texture);
```
<hr/>

## sfTexture_getSize - получить размер текстуры

Аргументы:

- ``const sfTexture* texture`` - текстура

**Возвращаемое значение:** ``sfVector2u`` - размер в пикселях

```c
CSFML_GRAPHICS_API sfVector2u sfTexture_getSize(const sfTexture* texture);
```
<hr/>

## sfTexture_copyToImage - преобразовать текстуру в изображение

Аргументы:

- ``const sfTexture* texture`` - текстура

**Возвращаемое значение:** ``sfImage*`` - изображение

```c
CSFML_GRAPHICS_API sfImage* sfTexture_copyToImage(const sfTexture* texture);
```
<hr/>

## sfTexture_updateFromPixels - обновить текстуру из массива

Аргументы:

- ``sfTexture* texture`` - текстура
- ``const sfUint8* pixels`` - массив пикселей, копируемых в текстуру
- ``unsigned int width`` - длина массива
- ``unsigned int height`` - высота массива
- ``unsigned int x`` - куда вставить массив по координате x
- ``unsigned int y`` - куда вставить массив по координате y

```c
CSFML_GRAPHICS_API void sfTexture_updateFromPixels(sfTexture* texture, const sfUint8* pixels, unsigned int width, unsigned int height, unsigned int x, unsigned int y);
```
<hr/>

## sfTexture_updateFromTexture - обновить часть текстуры из другой текстуры

Аргументы:

- ``sfTexture* destination`` - текстура назначения (куда обновлять)
- ``const sfTexture* source`` - исходная текстура (откуда брать)
- ``unsigned int x`` - куда вставить по координате x
- ``unsigned int y`` - куда вставить по координате y

```c
CSFML_GRAPHICS_API void sfTexture_updateFromTexture(sfTexture* destination, const sfTexture* source, unsigned int x, unsigned int y);
```
<hr/>

## sfTexture_updateFromImage - обновить часть текстуры из изображения

Аргументы:

- ``sfTexture* texture`` - текстура назначения (куда обновлять)
- ``const sfImage* image`` - изображение (откуда брать)
- ``unsigned int x`` - куда вставить по координате x
- ``unsigned int y`` - куда вставить по координате y

```c
CSFML_GRAPHICS_API void sfTexture_updateFromImage(sfTexture* texture, const sfImage* image, unsigned int x, unsigned int y);
```
<hr/>

## sfTexture_updateFromWindow - обновить часть текстуры из содержимого окна

Аргументы:

- ``sfTexture* texture`` - текстура назначения (куда обновлять)
- ``const sfWindow* window`` - окно (откуда брать)
- ``unsigned int x`` - куда вставить по координате x
- ``unsigned int y`` - куда вставить по координате y


```c
CSFML_GRAPHICS_API void sfTexture_updateFromWindow(sfTexture* texture, const sfWindow* window, unsigned int x, unsigned int y);
```
<hr/>

## sfTexture_updateFromRenderWindow - обновить часть текстуры из содержимого отрисовываемого окна

Аргументы:

- ``sfTexture* texture`` - текстура назначения (куда обновлять)
- ``const sfRenderWindow* renderWindow`` - отрисовываемое окно (откуда брать)
- ``unsigned int x`` - куда вставить по координате x
- ``unsigned int y`` - куда вставить по координате y

```c
CSFML_GRAPHICS_API void sfTexture_updateFromRenderWindow(sfTexture* texture, const sfRenderWindow* renderWindow, unsigned int x, unsigned int y);
```
<hr/>

## sfTexture_setSmooth - включить/отключить фильтр сглаживания текстуры

Аргументы:

- ``sfTexture* texture`` - текстура
- ``sfBool smooth`` - режим сглаживания (sfTrue - включить; sfFalse - отключить)

```c
CSFML_GRAPHICS_API void sfTexture_setSmooth(sfTexture* texture, sfBool smooth);
```
<hr/>

## sfTexture_isSmooth - узнать, включен ли фильтр сглаживания текстуры

Аргументы:

- ``const sfTexture* texture`` - текстура

**Возвращаемое значение:** ``sfBool`` - режим сглаживания (sfTrue - включен; sfFalse - отключен)

```c
CSFML_GRAPHICS_API sfBool sfTexture_isSmooth(const sfTexture* texture);
```
<hr/>

## sfTexture_setSrgb - включить/отключить преобразования sRGB

Это преобразование необходимо для автоматического распознования изображений в формате пикселей sRGB.

Большенство современных форматов изображений идут в правильном (линейном) формате и данный режим не требуется.
Но для некоторых изображений еще может потребоваться приобразование при работе с ними.

Данный режим включает двунаправленное преобразование цветов во всех операциях с изображениями для указанной текстуры.

После включения или отключения преобразования sRGB, для работы надстроек, необходимо перезагрузить текстуру.

Эта опция полезна только в сочетании с кадровым буфером, поддерживающим sRGB (можно активировать при создании окна).

Аргументы:

- ``sfTexture* texture`` - текстура
- ``sfBool sRgb`` - режим sRGB (sfTrue - включить; sfFalse - отключить)

```c
CSFML_GRAPHICS_API void sfTexture_setSrgb(sfTexture* texture, sfBool sRgb);
```
<hr/>

## sfTexture_isSrgb - узнать, включен ли режим sRGB

Аргументы:

- ``const sfTexture* texture`` - текстура

**Возвращаемое значение:** ``sfBool`` - режим sRGB (sfTrue - включен; sfFalse - отключен)

```c
CSFML_GRAPHICS_API sfBool sfTexture_isSrgb(const sfTexture* texture);
```
<hr/>

## sfTexture_setRepeated - включить/отключить режим повтора текстуры

Если область вывода больше размера текстуры, задействуется режим повтора текстуры. В режиме повтора, текстура будет заполнять пространство вывода постоянными повторениями.

Если выключить режим повторения текстуры, то пустое пространство (за текстурой), будет заполняться пикселями границы (из этой же текстуры).

ВНИМАНИЕ: на очень старых видеокартах при повторе текстуры, могут появиться белые пиксели. Для работы с такими картами (и вообще с любыми картами для увеличения скорости), лучше использовать текстуры, размеры которых кратны второй степени (например: 256x256, 256x512, 512x512, ...).

По умолчанию режим повтора отключен.

Аргументы:

- ``sfTexture* texture`` - текстура
- ``sfBool repeated`` - режим повтора (sfTrue - включить; sfFalse - отключить)

```c
CSFML_GRAPHICS_API void sfTexture_setRepeated(sfTexture* texture, sfBool repeated);
```
<hr/>


## sfTexture_isRepeated - проверить режим повтора текстуры

Аргументы:

- ``const sfTexture* texture`` - текстура

**Возвращаемое значение:** ``sfBool`` - режим повтора (sfTrue - включен; sfFalse - отключен)

```c
CSFML_GRAPHICS_API sfBool sfTexture_isRepeated(const sfTexture* texture);
```
<hr/>

## sfTexture_generateMipmap - генерация mipmap карты для текстуры

Mip-карты - это предварительно вычисленные цепочки оптимизированных текстур. Каждый уровень текстуры в MIP-карте создается путем циклического уменьшения размеров каждого из предыдущих уровней вдвое. И это уменьшение идет до тех пор, пока конечный уровень не станет размером 1x1.

То есть MIP-карта - это цепочка одной и тойже текстуры, у которой заранее просчитана её детализация при разных размерах. Каждый размер детализации имеет свой размер и своё изображение - уровень. Карта расчитывается от большего к меньшему в размерах во второй степени (поэтому лучше использовать текстуры с размерностью во второй степени).

К текстурам в MIP-картах, можно применять сложные фильтры обработки, а так же с ними быстрее работает рендер OpenGL.

ВНИМАНИЕ: Генерация Mipmap зависит от наличия необходимого расширения OpenGL. Если по какой либо причине, генерация не удалась, данная функция вернет sfFalse. Mipmap карты действительны с момента их создания до следующего изменения изображения базового уровня, после чего эту функцию необходимо будет снова вызвать для регенерации карт.

Аргументы:

- ``sfTexture* texture`` - текстура

**Возвращаемое значение:** ``sfBool`` - результат (sfTrue - гнерация прошла удачно; sfFalse - ошибка генерации, либо не доступно расширение OpenGL)

```c
CSFML_GRAPHICS_API sfBool sfTexture_generateMipmap(sfTexture* texture);
```
<hr/>

## sfTexture_swap - обменяться данными с другой текстурой

Работает как двойная буферизация (экономит время на отрисовке текстуры в памяти видеокарты).

Аргументы:

- ``sfTexture* left`` - текстура 1
- ``sfTexture* right`` - текстура 2

```c
CSFML_GRAPHICS_API void sfTexture_swap(sfTexture* left, sfTexture* right);
```
<hr/>

## sfTexture_getNativeHandle - получить базовый дескриптор текстуры в OpenGL.

Эта функция нужна для поддержки реализации дополнительных возможностей, которые не поддерживает SFML.

Аргументы:

- ``const sfTexture* texture`` - текстура

**Возвращаемое значение:** ``unsigned int`` - дескриптор текстуры или 0 - если текстура остутствует в OpenGL.

```c
CSFML_GRAPHICS_API unsigned int sfTexture_getNativeHandle(const sfTexture* texture);
```
<hr/>

## sfTexture_bind - связка текстуры с кодом OpenGL

Эта функция не является частью графического API и ее нельзя использовать при прорисовке объектов SFML. 
Её следует использовать, только если вам нужно использовать sfTexture с кодом OpenGL.

В один промежуток времени, можно связать одну текстуру (или работать по правилам стека OpenGL).

Аргументы:

- ``const sfTexture* texture`` - связываемая текстура с кодом OpenGL (NULL - отменить связку)

```c
CSFML_GRAPHICS_API void sfTexture_bind(const sfTexture* texture);
```

ПРИМЕР:
```c
sfTexture *t1, *t2;
...
sfTexture_bind(t1);
// рисуем в коде OpenGL используя t1...
sfTexture_bind(t2);
// рисуем в коде OpenGL используя t2...
sfTexture_bind(NULL);
// рисуем в коде OpenGL но теперь без текстур...
```
<hr/>

## sfTexture_getMaximumSize - получить максимальный размер текстуры

Информативная функция о поддержки размеров текстур OpenGL и видеоустройства.

**Возвращаемое значение:** ``unsigned int`` - Максимально-возможный размер текстуры.

```c
CSFML_GRAPHICS_API unsigned int sfTexture_getMaximumSize();
```
<hr/>

```c
#endif // SFML_TEXTURE_H
```
<hr/>

```c


