# Mutex.h - синхронизация доступа

Мьютекс - это семафор для процесса. При помощи таких семафоров, можно установить доступ к памяти в переменных, приостановив процессы, имеющие доступ к ним. 

Установив мьютекс в какой либо функции, можно заблокировать доступ от начала мьютекса до его разблокировки. При блокировки мьютекса, остальные процессы должны остановить своё выполнение до ожидания разблокировки мьютекса рабочим процессом. После того, как мьютекс разблокируется, его снова заблокирует первый процесс, который ждет своего выполнения и т.д.

```#include <SFML/System/Mutex.h>```
<hr/>

```c
#ifndef SFML_MUTEX_H
#define SFML_MUTEX_H

////////////////////////////////////////////////////////////
// Headers
////////////////////////////////////////////////////////////
#include <SFML/System/Export.h>
#include <SFML/System/Types.h>
```
<hr/>

## sfMutex_create - создать мьютекс

Устанавливает точку блокировки процессов.

Аргументы:

- **void** - отсутствуют

** Возвращаемое значение: sfMutex* ** - ссылка на мьютекс

```c
CSFML_SYSTEM_API sfMutex* sfMutex_create(void);
```
<hr/>

## sfMutex_destroy - удалить мьютекс

Мьютек необходимо удалить после его использования (высвободить память).

Аргументы:

-  **sfMutex* mutex** - удаляемый мьютекс

** Возвращаемое значение: void **

```c
CSFML_SYSTEM_API void sfMutex_destroy(sfMutex* mutex);
```
<hr/>

## sfMutex_lock - блокировать мьютекс

Блокирует доступ остальных процессов к данному участку памяти (запретить доступ).

Аргументы:

-  **sfMutex* mutex** - мьютекс для блокировки

** Возвращаемое значение: void **

```c
CSFML_SYSTEM_API void sfMutex_lock(sfMutex* mutex);
```
<hr/>

## sfMutex_unlock - разблокировать мьютекс

Разблокирует доступ остальных процессов к данному участку памяти (разрешить доступ).

Аргументы:

-  **sfMutex* mutex** - мьютекс для разблокировки

** Возвращаемое значение: void **

```c
CSFML_SYSTEM_API void sfMutex_unlock(sfMutex* mutex);
```
<hr/>

```c
#endif // SFML_MUTEX_H
```
<hr/>