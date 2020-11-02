# WindowHandle.h - дескриптор окна

```#include <SFML/Window/WindowHandle.h>```
<hr/>

## sfWindowHandle

Дескриптор окна зависит от операционной системы. Здесь приведен перевод определения дескриптора в CSFML. 

<hr/>

```c
#ifndef SFML_WINDOWHANDLE_H
#define SFML_WINDOWHANDLE_H

///////////////////////////////////////////////////////////////////////////////////////
// Используемые заголовочные файлы
///////////////////////////////////////////////////////////////////////////////////////
#include <SFML/Window/Export.h>


//////////////////////////////////////////////////////////////////////////////////////
// Определение низкоуровневого дескриптора окна, специфичный для каждой платформы
//////////////////////////////////////////////////////////////////////////////////////
#if defined(CSFML_SYSTEM_WINDOWS)

    // Если ОС Window, то дескриптор имеет тип HWND и ссылка (HWND__*)
    struct HWND__;
    typedef struct HWND__* sfWindowHandle;

#elif defined(CSFML_SYSTEM_LINUX) || defined(CSFML_SYSTEM_FREEBSD)

    // Если ОС Unix, Linux или базируется на оконном сервере X11, то дескриптор имеет тип unsigned long
    typedef unsigned long sfWindowHandle;

#elif defined(CSFML_SYSTEM_MACOS)

    // На Mac OS X или оконное ядро Cocoa - дескриптор окна имеет тип void*
	typedef void* sfWindowHandle;

#endif


#endif // SFML_WINDOWHANDLE_H
```
<hr/>
