# Thread.h - поток (процесс)

```#include <SFML/System/Thread.h>```
<hr/>


```c
#ifndef SFML_THREAD_H
#define SFML_THREAD_H

////////////////////////////////////////////////////////////
// Headers
////////////////////////////////////////////////////////////
#include <SFML/System/Export.h>
#include <SFML/System/Types.h>
```
<hr/>

## sfThread_create - создает новый процесс

Аргументы:

- **void (*function)(void*)** - указатель на функцию, которая запустится в новом процессе
- **void* userData** - пользовательские данные в аргументе функции

** Возвращаемое значение: sfThread* ** - ссылка на процесс

```c
CSFML_SYSTEM_API sfThread* sfThread_create(void (*function)(void*), void* userData);
```
<hr/>

## sfThread_destroy - удалить процесс 

Безопасное удаление процесса. Данная функция перед удалением процесса вызовет sfThread_wait и попытается остановить процесс освободив память занятыми данными.

АргументыЖ

- **vsfThread* thread** - ссылка на процесс, который нужно удалить

** Возвращаемое значение: void **

```c
CSFML_SYSTEM_API void sfThread_destroy(sfThread* thread);
```
<hr/>

## sfThread_launch - запустить процесс

Функция запустит ранее созданный процесс паралельно текущему процессу. Текущий процесс также продолжит работу.

Аргументы:

- **vsfThread* thread** - ссылка на процесс, который нужно запустить

** Возвращаемое значение: void **

```c
CSFML_SYSTEM_API void sfThread_launch(sfThread* thread);
```
<hr/>

## sfThread_wait - ожидание выполнения процесса

Ожидает завершение указанного процесса. Текущий процесс приостанавливает работу. Требуется для синхронизации.

Аргументы:

- **vsfThread* thread** - ссылка на процесс, завершение которого продолжит работу дальше

** Возвращаемое значение: void **

```c
CSFML_SYSTEM_API void sfThread_wait(sfThread* thread);
```
<hr/>

## sfThread_terminate - жесткое завершение процесса

Немедленно останавливает указанный процесс. Данная функция не ждет завершение процесса и не высвобождает память переменных, задействованных в работе процесса.

Лучше дождаться выполнения процесса функцией sfThread_wait и уже затем, вызвать sfThread_terminate.
 
Аргументы:

- **vsfThread* thread** - ссылка на процесс, который нужно удалить

** Возвращаемое значение: void **

```c
CSFML_SYSTEM_API void sfThread_terminate(sfThread* thread);
```
<hr/>


```c
#endif // SFML_THREAD_H
```
<hr/>
