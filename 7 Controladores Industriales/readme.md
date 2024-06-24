# Módulo 7: Controladores Industriales

El desarrollo del proyecto relevante a controladores industriales, corresponde a la lógica que se debió programar para el correcto funcionamiento de los gemelos digitales de las máquinas de la propuesta de automatización. Como metodología general, aprovechamos la utilización de Sequential Function Charts dentro de Studio5000, empleando el estandar GRAFCET para poder realizar todas las rutinas de movimiento. El flujo de trabajo que se empleó para realizar la programación fue el siguiente:

![DiagramaDeFlujo_Modulo7 drawio](https://github.com/danielCamiloP/TecnomecatroniX/assets/37418973/b46ffb5b-81d6-4a88-8cf1-6a6a4111888c)

Con esta metodología pudimos llegar a las subrutinas del programa para el PLC que controla toda la simulación de fábrica digital, las cuales se presentan en el documento [RutinasPLC.pdf](./RutinasPLC.pdf).
Se recomienda descargar el archivo y emplear el zoom para visualizar los GRAFCET, dado que por su tamaño la única forma de visualizarlos es emplear este método.

En la carpeta ProgramaStudio5000 se encuentra el programa definitivo usado para la simulación de la planta en NX.

A continuación se explicará las rutinas implementadas en el gemelo digital:

## Prensa Grafcet

El programa de control para la prensa inicia con la activación de un comando "startPress", dando inicio al ciclo de producción. En primer lugar, el sistema retrae el actuador encargado de sacar las baldosas prensadas hacia la banda transportadora, preparando así la estación para un nuevo ciclo.

Durante el proceso, dos operaciones críticas se llevan a cabo en paralelo: por un lado, la prensa aplica la fuerza necesaria sobre las baldosas en el molde y posteriormente un actuador se eleva para levantar las baldosas ya prensadas. Este paso asegura que las piezas adquieran la forma deseada y se preparen para el siguiente paso del proceso.

Mientras tanto, otro sistema comienza a llenar el molde con polvo de arcilla mediante actuadores lineales, asegurando una distribución uniforme del material. Una vez completados estos dos procesos, el primer actuador vuelve a entrar en acción para extraer las baldosas prensadas y levantadas hacia la banda transportadora, concluyendo así un ciclo de producción, quedando preparado para el siguiente.

Para una visualización clara y detallada del proceso de control, se incluyen dos elementos visuales esenciales:

Diagrama de Flujo: Este diagrama representa gráficamente el flujo secuencial del programa de control de la prensa. 
![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/82681128/d995cada-a3ae-4b7f-89f6-651393f9d5c4)

GRAFCET desde Studio 5000: El GRAFCET generado desde el entorno de desarrollo Studio 5000 

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/82681128/e467dafc-a84e-4ea5-8b32-8c6bda985e01)

## Volteadora Grafcet

El ciclo de operación de la volteadora se inicia con la activación de un comando "start", lo que enciende los rodillos de la máquina para el transporte de las baldosas. A continuación, el sistema bifurca el flujo de trabajo usando una operación OR: si la volteadora se encuentra en posición 0°, las baldosas activarán el sensor 1 al pasar por la posición correcta. Por otro lado, si la volteadora está en posición 180°, las baldosas activarán el sensor 2.

Posteriormente los rodillos de la volteadora se detienen temporalmente para permitir que las baldosas se posicionen adecuadamente según la detección del sensor correspondiente. Acto seguido, los actuadores lineales entran en acción para aplicar presión sobre las baldosas, asegurando un contacto firme y uniforme en su lugar de trabajo.

Un actuador rotacional entonces gira las baldosas 180° en una dirección específica, dependiendo de la posición inicial detectada por los sensores

Finalmente, se reactivan los rodillos de la volteadora para permitir que las baldosas continúen su trayectoria hacia la fase siguiente del proceso.

Diagrama de Flujo: Este diagrama representa gráficamente el flujo secuencial del programa de control de la volteadora. 
![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/82681128/efa7e8bb-0553-4647-b4af-b24f84410c5f)

GRAFCET desde Studio 5000: El GRAFCET generado desde el entorno de desarrollo Studio 5000 

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/82681128/456984ba-c78a-435f-bf4e-0f7d7e109eb6)


## Celda robotica Grafcet

El ciclo de operación de la celda robotizada comienza con la espera de una señal de "ready", indicando que el sistema está listo para recibir las cajas a paletizar. Una vez recibida esta señal, la celda robotizada espera la llegada de un AGV (Vehículo Guiado Automáticamente) que transporta las cajas hacia la estación de paletizado.

Una vez que el AGV y las cajas llegan a la posición adecuada, la celda robotizada procede a paletizar las cajas según un número predeterminado que indica cuántas cajas deben ser colocadas en cada palet.

Después de completar el paletizado, la celda robotizada activa el AGV para que continúe con su ruta asignada, quedando preparado para el siguiente ciclo. Mientras tanto, el sistema de control de la celda robotizada siempre verifica la presencia de una señal de parada de emergencia; si se detecta esta condición, se detiene inmediatamente toda la operación para garantizar la seguridad del entorno y del personal.

Diagrama de Flujo: Este diagrama representa gráficamente el flujo secuencial del programa de control de la celda robotizada. 

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/82681128/aa4df83e-5c0d-4953-bc1b-9d93a2d1bc8e)



