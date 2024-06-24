# Módulo 7: Controladores Industriales

El desarrollo del proyecto relevante a controladores industriales, corresponde a la lógica que se debió programar para el correcto funcionamiento de los gemelos digitales de las máquinas de la propuesta de automatización. Como metodología general, aprovechamos la utilización de Sequential Function Charts dentro de Studio5000, empleando el estandar GRAFCET para poder realizar todas las rutinas de movimiento. El flujo de trabajo que se empleó para realizar la programación fue el siguiente:

![DiagramaDeFlujo_Modulo7 drawio](https://github.com/danielCamiloP/TecnomecatroniX/assets/37418973/b46ffb5b-81d6-4a88-8cf1-6a6a4111888c)

Con esta metodología pudimos llegar a las subrutinas del programa para el PLC que controla toda la simulación de fábrica digital, las cuales se presentan en el documento [RutinasPLC.pdf](./RutinasPLC.pdf).
Se recomienda descargar el archivo y emplear el zoom para visualizar los GRAFCET, dado que por su tamaño la única forma de visualizarlos es emplear este método.

En la carpeta ProgramaStudio5000 se encuentra el programa definitivo usado para la simulación de la planta en NX.

A continuación se explicará las rutinas implementadas en el gemelo digital:

## Prensa 

El programa de control para la prensa inicia con la activación de un comando "startPress", dando inicio al ciclo de producción. En primer lugar, el sistema retrae el actuador encargado de sacar las baldosas prensadas hacia la banda transportadora, preparando así la estación para un nuevo ciclo.

Durante el proceso, dos operaciones críticas se llevan a cabo en paralelo: por un lado, la prensa aplica la fuerza necesaria sobre las baldosas en el molde y posteriormente un actuador se eleva para levantar las baldosas ya prensadas. Este paso asegura que las piezas adquieran la forma deseada y se preparen para el siguiente paso del proceso.

Mientras tanto, otro sistema comienza a llenar el molde con polvo de arcilla mediante actuadores lineales, asegurando una distribución uniforme del material. Una vez completados estos dos procesos, el primer actuador vuelve a entrar en acción para extraer las baldosas prensadas y levantadas hacia la banda transportadora, concluyendo así un ciclo de producción, quedando preparado para el siguiente.

Para una visualización clara y detallada del proceso de control, se incluyen dos elementos visuales esenciales:

Diagrama de Flujo: Este diagrama representa gráficamente el flujo secuencial del programa de control de la prensa. 
![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/82681128/d995cada-a3ae-4b7f-89f6-651393f9d5c4)

GRAFCET desde Studio 5000: El GRAFCET generado desde el entorno de desarrollo Studio 5000 

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/82681128/e467dafc-a84e-4ea5-8b32-8c6bda985e01)

## Volteadora

El ciclo de operación de la volteadora se inicia con la activación de un comando "start", lo que enciende los rodillos de la máquina para el transporte de las baldosas. A continuación, el sistema bifurca el flujo de trabajo usando una operación OR: si la volteadora se encuentra en posición 0°, las baldosas activarán el sensor 1 al pasar por la posición correcta. Por otro lado, si la volteadora está en posición 180°, las baldosas activarán el sensor 2.

Posteriormente los rodillos de la volteadora se detienen temporalmente para permitir que las baldosas se posicionen adecuadamente según la detección del sensor correspondiente. Acto seguido, los actuadores lineales entran en acción para aplicar presión sobre las baldosas, asegurando un contacto firme y uniforme en su lugar de trabajo.

Un actuador rotacional entonces gira las baldosas 180° en una dirección específica, dependiendo de la posición inicial detectada por los sensores

Finalmente, se reactivan los rodillos de la volteadora para permitir que las baldosas continúen su trayectoria hacia la fase siguiente del proceso.

Diagrama de Flujo: Este diagrama representa gráficamente el flujo secuencial del programa de control de la volteadora. 
![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/82681128/efa7e8bb-0553-4647-b4af-b24f84410c5f)

GRAFCET desde Studio 5000: El GRAFCET generado desde el entorno de desarrollo Studio 5000 

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/82681128/456984ba-c78a-435f-bf4e-0f7d7e109eb6)

## Secadora

Dado que el proceso dentro de la secadora se simuló como un movimiento continuo a través de la máquina, no se realizó una rutina Grafcet como tal, sino solo el control directo de la banda transportadora que atraviesa esta máquina.

## Bifurcación

El diagrama de flujo planteado se observa a continuación.

![Captura de pantalla 2024-06-23 232634](https://github.com/danielCamiloP/TecnomecatroniX/assets/52110700/ce79226f-da9f-47fc-8ade-2be385d8f9b9)

Y el código grafcet implementado:

![Captura de pantalla 2024-06-23 222909](https://github.com/danielCamiloP/TecnomecatroniX/assets/52110700/2f892763-16a1-4d98-89ef-637a50b926c4)

El código es para hacer una bifurcación de dos caminos de bandas transportadoras para una línea de cerámicas,

El paso inicial es activar la banda B1 y B2A y desactivar B2B, a partir de esto, por la banda B1 va a venir las tandas de 4 baldosas, el sensor S1 detectará el paso de las baldosas, como son tandas de 4, estará asociado un contador (C1) que contará hasta 4, (cuenta por la activación del sensor), al contar hasta 4 el sistema sabrá que pasó la primera tanda, entonces al activarse S2 y S1 al tiempo, se para la banda B1 y se activa la banda B2 en la dirección definida por el bit P (si es 1 va por un camino, se es 0 va por el otro).

Si va por el camino B2B, entonces la banda B1 permanecerá apagada hasta que el S2 se apague, es decir, hasta que la banda B2 esté libre y así poder reactivar B1 para el paso de la siguiente tanda.

Si el camino va por B2A, entonces la banda B1 permanecerá apagada hasta que el contador C2 asociado a S2 cuente 4 baldosas, significando que las 4 baldosas ya pasaron por la banda B2, es decir que esta ya está libre para el paso de las siguientes baldosas.

## Esmalte y engobe

Los procesos de esmalte y engobe son procesos continuos donde las máquinas siempre están prendidas y las baldosas solo pasan por allí, así como en la secadora, para estos no se realiza un programa de Grafcet.

## Unión 

El diagrama de flujo planteado se observa a continuación:

![Diagrama_Union](https://github.com/danielCamiloP/TecnomecatroniX/assets/52110700/f46302ac-a724-4f5f-b0ed-c8f04f31051d)

Y el correspondiente programa en Grafcet:

![Captura de pantalla 2024-06-24 094142](https://github.com/danielCamiloP/TecnomecatroniX/assets/52110700/ce8bbe63-d819-42c9-87db-5f6c7921411d)
 engobe

El diagrama de flujo comienza con la activación de BDer, BIzq y B_unión en X, seguido de una espera para la activación de SDer o SIzq. Si SIzq se activa primero, se espera 3 segundos y luego se verifica si SDer se activa; si es así, se apaga BDer para evitar que lleguen baldosas de ambos caminos, y si no, se espera hasta que SIzq se apague significando que la banda de unión ya está desocupada y puede permitir el paso de otra tanda de baldosas. Si SDer se activa primero, se enciende B_unión en Y, se espera 2 segundos para que las baldosas entren por completo en la banda de unión y se apaga BDer para evitar posibles colisiones. Posteriormente, si SIzq se activa, se apaga BIzq para evitar el flujo de baldosas por ambos caminos; de lo contrario, se espera la activación de SUnión. Si SUnión se activa, significa que las baldosas ya están en la banda de unión, entonces se enciende BUnion en X y se espera 2.5 segundos para que las baldosas se retiren de la banda de unión. El proceso sigue este ciclo, volviendo a esperar a la llegada de baldosas por medio de SDer y SIzq.

## Decoradora y horno

La misma situación del esmalte, engobe y secadora.

## Control de calidad

El diagrama de flujo correspondiente se observa a continuación:

![QC_ladder](https://github.com/danielCamiloP/TecnomecatroniX/assets/52110700/55eb2263-5e06-4c6e-b3ec-2c7583b85669)


En este caso se implementó el Ladder a modo Grafcet solicitado:

![laddGraf](https://github.com/danielCamiloP/TecnomecatroniX/assets/52110700/2635d3f9-fe49-43af-9eab-5d0a61d79577)

El proceso comienza contando baldosas con el sensor S_QC. Si la baldosa pasa el control de calidad (QC), se carga un '1' en la FIFO; si no pasa, se carga un '0' en la FIFO. Luego, se verifica si la FIFO está llena. Si está llena, significa que ya toda la tanda de baldosas pasó por la máquina de QC, entonces pasan a la siguiente etapa que es el kicker, que desplaza las baldosas que NO pasan el control de calidad, entonces se cuenta la baldosa en el kicker con un sensor, se extrae el dato de la cima de la FIFO y se lee. Si la baldosa no pasó el QC según el dato leído ('0'), se enciende el kicker para quitar la baldosa. Si la baldosa pasó el QC  ('1'), no se hace nada (la banda continúa sin que se encienda el kicker). Posteriormente, se verifica si la FIFO está vacía. Si la FIFO no está vacía, se verifica la siguiente baldosa con el siguiente dato en la cima de la FIFO volviendo a repetir este ciclo. Si la FIFO ya está vacía, el proceso regresa al inicio y cuenta nuevamente baldosas con S_QC.

## Celda robotica 

El ciclo de operación de la celda robotizada comienza con la espera de una señal de "ready", indicando que el sistema está listo para recibir las cajas a paletizar. Una vez recibida esta señal, la celda robotizada espera la llegada de un AGV (Vehículo Guiado Automáticamente) que transporta las cajas hacia la estación de paletizado.

Una vez que el AGV y las cajas llegan a la posición adecuada, la celda robotizada procede a paletizar las cajas según un número predeterminado que indica cuántas cajas deben ser colocadas en cada palet.

Después de completar el paletizado, la celda robotizada activa el AGV para que continúe con su ruta asignada, quedando preparado para el siguiente ciclo. Mientras tanto, el sistema de control de la celda robotizada siempre verifica la presencia de una señal de parada de emergencia; si se detecta esta condición, se detiene inmediatamente toda la operación para garantizar la seguridad del entorno y del personal.

Diagrama de Flujo: Este diagrama representa gráficamente el flujo secuencial del programa de control de la celda robotizada. 

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/82681128/aa4df83e-5c0d-4953-bc1b-9d93a2d1bc8e)



