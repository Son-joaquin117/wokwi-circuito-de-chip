<!---

This file is used to generate your project datasheet. Please fill in the information below and delete any unused
sections.

You can also include images in this folder and reference them in the markdown. Each image must be less than
512 kb in size, and the combined size of all images must be less than 1 MB.
-->

## How it works
El proyecto consiste en un sistema de alarma digital implementado con compuertas lógicas. Su funcionamiento se basa en evaluar distintas condiciones de entrada (sensores) para determinar cuándo activar una alerta (LED o buzzer).

El sistema utiliza tres señales de entrada:

A (Puerta): representa si una puerta o ventana ha sido abierta (sensor magnético).
B (Sistema activado): indica si la alarma está encendida o habilitada mediante un interruptor.
C (Humo): representa la detección de humo en el ambiente mediante un sensor.

La lógica implementada sigue la siguiente expresión:

SALIDA = (A AND B) OR C

Esto significa:

La alarma se activará si la puerta está abierta Y el sistema está activado.
También se activará si se detecta humo, sin importar el estado de las otras entradas.
Funcionamiento paso a paso:
Las señales A y B entran a una compuerta AND.
La salida de esta compuerta será 1 solo cuando ambas entradas sean 1.
Esa salida se conecta a una compuerta OR junto con la señal C.
Si cualquiera de las entradas del OR es 1, la salida final se activa.
La salida final controla un LED o buzzer, que representa la alarma.

Este comportamiento permite simular un sistema de seguridad básico, donde múltiples condiciones pueden disparar una alerta.

## How to test
Para probar el funcionamiento del circuito, se deben simular las entradas utilizando interruptores (como DIP switches o botones).

Pasos para probar:
Conectar las entradas:
A (puerta) → interruptor 1
B (sistema activado) → interruptor 2
C (humo) → interruptor 3
Encender el circuito:
Asegurarse de que los chips estén correctamente alimentados (5V y GND).
Probar diferentes combinaciones:
Caso 1:
A = 1, B = 1, C = 0
→ Resultado: alarma ACTIVADA
Caso 2:
A = 1, B = 0, C = 0
→ Resultado: alarma APAGADA
Caso 3:
A = 0, B = 0, C = 1
→ Resultado: alarma ACTIVADA
Caso 4:
A = 0, B = 0, C = 0
→ Resultado: alarma APAGADA
Verificar la salida:
Si usas un LED: debe encenderse cuando la alarma esté activa.
Si usas un buzzer: debe emitir sonido.

## External hardware
Interruptores (DIP switch o pulsadores): para simular las entradas A, B y C.
LED o buzzer: como dispositivo de salida para indicar la activación de la alarma.
Resistencias: para proteger el LED y asegurar un funcionamiento correcto.
Sensor magnético (reed switch): utilizado para detectar la apertura de puertas o ventanas (entrada A).
Sensor de humo (por ejemplo MQ-2): utilizado para detectar la presencia de humo en el ambiente (entrada C).
