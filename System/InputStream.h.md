# InputStream.h - поток ввода

Описание потока ввода нужно - для совместного использования ввода/вывода программы и SFML (написание драйвера).

```#include <SFML/System/InputStream.h>```
<hr/>


```c
#ifndef SFML_INPUTSTREAM_H
#define SFML_INPUTSTREAM_H

////////////////////////////////////////////////////////////
// Headers
////////////////////////////////////////////////////////////
#include <SFML/System/Export.h>
```
<hr/>

## Обработчики обратных вызовов

```c
typedef sfInt64 (*sfInputStreamReadFunc)(void* data, sfInt64 size, void* userData);
typedef sfInt64 (*sfInputStreamSeekFunc)(sfInt64 position, void* userData);
typedef sfInt64 (*sfInputStreamTellFunc)(void* userData);
typedef sfInt64 (*sfInputStreamGetSizeFunc)(void* userData);
```
<hr/>

## sfInputStream - описание потока

```c
typedef struct sfInputStream
{
    sfInputStreamReadFunc    read;     ///< Функция чтения данных из потока
    sfInputStreamSeekFunc    seek;     ///< Функция для установки текущей позиции чтения
    sfInputStreamTellFunc    tell;     ///< Функция для получения текущей позиции чтения
    sfInputStreamGetSizeFunc getSize;  ///< Функция для получения общего количества байтов в потоке
    void*                    userData; ///< Пользовательские данные, которые будут переданы в обратные вызовы
} sfInputStream;
```
<hr/>

