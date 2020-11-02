# JoystickIdentification.h - определение джойстика

```#include <SFML/Window/JoystickIdentification.h>```
<hr/>



```c
#ifndef SFML_JOYSTICKIDENDIFICATION_H
#define SFML_JOYSTICKIDENDIFICATION_H

////////////////////////////////////////////////////////////
// Headers
////////////////////////////////////////////////////////////
#include <SFML/Window/Export.h>
```
<hr/>

## sfJoystickIdentification - структура определения джойстика

```c
typedef struct
{
    const char*  name;
    unsigned int vendorId;
    unsigned int productId;
} sfJoystickIdentification;
```
<hr/>

```c
#endif // SFML_JOYSTICKIDENDIFICATION_H
```








