# Introducción a la "Informática" y Arquitectura de Sistemas

Antes de hablar de seguridad o de buscar vulnerabilidades, necesitamos entender qué estamos protegiendo. Intentar defender (o auditar) un sistema que no entiendes es como intentar proteger un edificio sin conocer sus planos ni sus puertas de acceso.

En esta sala se exploró por completo el sistema, viendo cómo están conectados sus bloques básicos. El objetivo es tener una idea general de cómo interactúan los componentes de un sistema informático entre sí para ofrecer servicio a los usuarios.

Casi todos los sistemas informáticos están compuestos por los mismos "bloques". Cada parte tiene su propio funcionamiento u objetivo a cumplir y, juntos, hacen que el sistema funcione.

## Partes Fundamentales de un Sistema

A continuación, exploramos la función de cada bloque y su rol dentro de la arquitectura de la máquina:

### 1. Motherboard (Tarjeta Madre)
Es la columna vertebral del sistema. Se trata de la placa de circuito impreso principal que permite la comunicación entre todos los demás componentes. Define qué tipo de CPU puedes usar, cuánta RAM soporta y cuántos periféricos puedes conectar.

### 2. CPU (Unidad Central de Procesamiento)
El "cerebro" del sistema. Es el encargado de ejecutar las instrucciones de los programas y del sistema operativo. Realiza operaciones aritméticas, lógicas y de entrada/salida de datos. 

### 3. RAM (Memoria de Acceso Aleatorio)
Es la memoria de trabajo temporal. Cuando abres un programa, sus datos se cargan desde el almacenamiento a la RAM para que la CPU pueda acceder a ellos a velocidades altísimas. Al apagar el equipo, esta información se pierde.

### 4. GPU (Unidad de Procesamiento Gráfico)
Procesador altamente paralelo especializado en realizar miles de cálculos matemáticos al mismo tiempo. En ciberseguridad, las GPUs se utilizan intensivamente para el craqueo de contraseñas mediante fuerza bruta.

### 5. HDD o SSD (Almacenamiento)
Es la memoria permanente del sistema donde residen el sistema operativo, los programas y los archivos.
* **HDD (Disco Duro Mecánico):** Usa platos magnéticos giratorios. Más lento pero económico.
* **SSD (Unidad de Estado Sólido):** Usa memoria flash. Es considerablemente más rápido.

### 6. PSU (Fuente de Poder)
Se encarga de recibir la corriente alterna del enchufe y transformarla en corriente continua que los componentes electrónicos pueden usar. 

---

## ¿Qué es el Firmware?

En términos sencillos, el firmware es el "software del hardware". Es un tipo específico de código que proporciona el control de bajo nivel para el hardware de un dispositivo. 
Sirve como puente o traductor inicial entre los componentes físicos y el sistema operativo. A diferencia de tus archivos que se guardan en el disco duro, el firmware viene preinstalado de fábrica y se almacena directamente en chips de memoria especial en la placa del propio dispositivo. 

Sin firmware, ninguna pieza de hardware sabría cómo encender ni cómo comunicarse con el resto del equipo.

---

## El Proceso de Arranque (Boot Process)

Ahora que los componentes principales están instalados en el sistema informático, es hora de arrancar el sistema. Podemos comparar esto con cómo nos despertamos por la mañana y hacemos una comprobación rápida para ver si todo funciona. Solo cuando todo está bien, nos levantamos y empezamos nuestro día. 

Estos son los pasos que sigue un sistema informático antes de mostrarte una interfaz funcional (en forma de un sistema operativo):

* **Paso 1: Pulsa el botón de encendido.** 
Cuando pulsamos el botón de encendido en nuestro sistema informático, se envía una señal a la fuente de alimentación para permitir el flujo de energía. Imagina que nuestro cuerpo está apagado cuando dormimos. Una vez que despertamos y recibimos oxígeno, nuestro cuerpo empieza a bombear sangre y a activarse.

* **Paso 2: Empieza el firmware.** 
Siguiendo con nuestra analogía del paso 1, una vez que el cuerpo ha arrancado, nuestros componentes principales están funcionando, pero nuestro cerebro aún no está consciente. Al igual que nuestros cuerpos, un sistema informático contiene un firmware que permite que todos sus componentes se inicien. El sistema central que gestiona esto se llama Interfaz Unificada de Firmware Extensible (UEFI). 
*Nota: A menudo veremos el término BIOS mencionado en lugar de UEFI. BIOS hace lo mismo que UEFI, pero ha sido reemplazado principalmente por este último.*

* **Paso 3: Autoprueba de encendido (POST).** 
Ahora que nuestro cuerpo está funcionando, es hora de comprobar si todo funciona como debe. Si algo no lo está, habrá señales de alarma. Una de las rutinas que carga el UEFI es la Autoprueba de Encendido (POST - Power-On Self-Test), que evalúa si todos los componentes necesarios están presentes, correctamente configurados y funcionando.

* **Paso 4: Seleccione dispositivo de arranque.** 
Una vez que nuestro cuerpo está funcionando, configurado correctamente y totalmente funcional, nuestro sistema busca la ubicación de nuestra rutina de arranque para iniciar nuestra conciencia. En nuestro sistema informático, el UEFI contiene una lista ordenada que prioriza qué dispositivo buscar primero para la rutina de arranque del Sistema Operativo.

* **Paso 5: Iniciar el bootloader.** 
Ahora que nuestro sistema conoce la parte de nuestro cerebro donde está nuestra conciencia, inicia la "rutina de carga" para iniciarla. Nuestros sistemas informáticos siguen un proceso similar: en el dispositivo de arranque seleccionado, se inicia el cargador de arranque (bootloader). Este gestor de arranque transfiere el núcleo del sistema operativo desde el dispositivo de almacenamiento a la memoria de acceso aleatorio (RAM). Una vez que el OS (Operating System) se transfiere, el UEFI cede el control sobre los diferentes componentes al Sistema Operativo.

---
**Conclusión:**
Todas estas partes son indispensables. En esta sala se logró comprender la ubicación de las piezas, su funcionalidad individual y cómo interactúan desde el momento de presionar el botón de encendido hasta la carga del sistema, sentando las bases físicas sobre las cuales corren las redes y las barreras de seguridad. 

Más adelante se comprenderá mejor el motivo por el cual se estudia la arquitectura a este nivel. En muchas ocasiones, los atacantes intentan vulnerar el proceso de arranque (buscando comprometer el equipo antes de que el sistema operativo y las defensas se inicien), por lo que conocer este flujo es vital para entender por dónde buscan entrar y cómo asegurar un sistema desde su encendido.