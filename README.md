# Mando Rally — PedreiraTech

Código Arduino del mando Bluetooth para roadbook basado en **ESP32-C3**, creado por **PedreiraTech**.

## Funciones
- Cinco controles físicos configurables.
- Tres perfiles de botones guardados en memoria.
- Control multimedia y teclas de teclado mediante Bluetooth LE.
- Configuración desde una página web en modo Wi-Fi.
- Actualización de firmware por Wi-Fi mediante archivo `.bin`.

## Archivos
- `MandoRallyFinal.ino`: programa principal para abrir con Arduino IDE.

## Hardware y conexiones
El firmware usa botones conectados entre cada GPIO y **GND**, con resistencias pull-up internas (`INPUT_PULLUP`).

| Control | GPIO |
|---|---|
| Botón 1 | 4 |
| Botón 2 | 5 |
| Botón 3 | 3 |
| Palanca abajo | 2 |
| Palanca arriba | 0 |

**Importante:** estas conexiones corresponden a esta versión concreta del firmware. Comprueba el cableado antes de cargarlo.

## Instalación
1. Instala Arduino IDE y el soporte para placas **ESP32**.
2. Instala la biblioteca **ESP32 BLE Keyboard** que proporciona `BleKeyboard.h` y comprueba su compatibilidad con tu versión del núcleo ESP32.
3. Abre `MandoRallyFinal.ino` en Arduino IDE.
4. Selecciona la placa ESP32-C3 correspondiente y su puerto.
5. Compila y carga el programa por USB.
6. Busca por Bluetooth el dispositivo **Mando Rally Final** (nombre predeterminado).

No se ha verificado aquí la compilación ni se ha probado este firmware en hardware.

## Configuración Wi-Fi
Mantén pulsados **Botón 1 + Palanca abajo durante 5 segundos** para entrar en modo actualización/configuración. Conéctate a la red `MandoRally-Update` con la contraseña configurada en el archivo `.ino` y abre **http://192.168.4.1**.

Desde la web puedes cambiar el nombre Bluetooth, editar tres perfiles y subir un firmware `.bin`.

Para salir del modo actualización, mantén **Botón 1 + Palanca abajo durante 3 segundos** o reinicia desde la página web. Si nadie se conecta al punto de acceso durante 10 minutos, se reinicia automáticamente.

En funcionamiento Bluetooth, **Botón 1 + Palanca arriba durante 5 segundos** reinicia el mando.

## Precauciones
- El modo Wi-Fi utiliza una contraseña fija de ejemplo en el código: cámbiala antes de utilizar el firmware en entornos públicos.
- Las acciones multimedia suelen tener mejor compatibilidad; las teclas normales pueden no funcionar con todos los dispositivos.
- Antes de actualizar por Wi-Fi, conserva una copia del firmware funcional y verifica el archivo `.bin`.

## Autor
**PedreiraTech Solutions** — @PedreiraTechSolutions

## Licencia
No se ha añadido una licencia de reutilización. Todos los derechos quedan reservados salvo que el autor publique una licencia explícita.
