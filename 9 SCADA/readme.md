# [SCADA](http://ignition-cloud-apm.dwgsfugwegg6g6hc.eastus.azurecontainer.io:8088/data/perspective/client/Ignition_nube)

Como parte final de nuestro proyecto, hemos implementado un sistema SCADA para optimizar los procesos de manufactura de nuestra propuesta para planta de producción de cerámica. Este sistema integra sistemas basados en HMI, Azure e Ignition para monitoreo, supervisión y control industrial, El link a la interfaz está alojado en: (http://ignition-cloud-apm.dwgsfugwegg6g6hc.eastus.azurecontainer.io:8088/data/perspective/client/Ignition_nube).

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/82681128/c75cc323-2d21-48d2-b50c-53a746bd0152)


En esta interfaz podemos navegar a través de los botones del lado izquierdo, además de previsualizar alarmas en la parte inferior. Como vemos, en estos momentos solo se tiene activadas las etaciones de la prensa, la volteadora, la estacion de engobe y esmaltado y el paletizado, si accedemos a cada monitoreo de la máquina podemos ver el estado de cada máquina.

En el prensado podemos supervisar estados como la activacion de la prensa y la cantidad de baldosas que se producen.

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/82681128/4456e5a6-86b2-4fbf-926e-965287860616)

En la volteadora podemos supervisar estados como la activacion de la volteadora, la posicion angular del rotor y la cantidad de baldosas que se voltean.

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/82681128/18c09e45-7161-43f2-98c6-5174f0ff2f6d)


En la estacion de emsalte y engobe podemos supervisar estados como la activacion de la volteadora, ademas de poder controlar desde el scada la direccion de las baldosas.

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/82681128/18486b3c-5929-4461-8269-3207f922d4fe)

En la estacion de control de calidad podemos supervisar estados como la activacion de la estacion y el momento en el que hay una baldosa defectuosa.

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/82681128/d9697f39-1cf8-41d6-8b21-5e5fb2fa1a57)

En la celda robotica podemos supervisar estados como la activacion de la estacion, las cajas paletizadas, la cantidad de lotes peletizados y el total de baldosas paletizadas ademas de poder operar el tamaño del lote por pallet y por ultimo se cuenta con un indicador para la parada de emergencia si se activa la cortina laser.

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/82681128/b15bf646-88dc-4026-a26e-e6b2e5339897)


Finalmente, podemos observar algunas alarmas,como la activacion de la prensa, la volteadora, la celda y su desactivacion, ademas de otras situaciones importantes como el prensado, el giro de la volteadora o  la ocurrencia de una parada de emergencia, lo cual nos permite tener conocimiento del estado de la planta.

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/82681128/e2a2fc1c-fca3-416f-984d-1a7a4dcae6c3)


Ademas se realizo la implementacion de los historicos de 6 señales, las cuales fueron, tiempó de funcionamiento de la prensa, tiempó de funcionamiento de la voltradora, tiempó de funcionamiento de la celda, cantidad de baldosas volteadas, cantidad de baldosas prensadas y tiempo de paradas de emergencia.  
![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/82681128/35b28152-3e59-4019-8aa0-7cf287ed6559)




