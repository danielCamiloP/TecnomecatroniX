# SCADA

Como parte final de nuestro proyecto, hemos implementado un sistema SCADA para optimizar los procesos de manufactura de nuestra propuesta para planta de producción de cerámica. Este sistema integra sistemas basados en HMI, Azure e Ignition para monitoreo, supervisión y control industrial.

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



Finalmente, podemos observar datos historizados y datos de alarma, que nos permite tener el estado de la planta.

![alarmas](https://github.com/danielCamiloP/TecnomecatroniX/assets/49196698/e045a114-6122-4df4-9e5a-87b58cf34aa7)


![historicos](https://github.com/danielCamiloP/TecnomecatroniX/assets/49196698/d68425c7-f450-4ece-8733-ba05b859dffd)


El link a la interfaz está alojado en: (http://ignition-cloud-apm.dwgsfugwegg6g6hc.eastus.azurecontainer.io:8088/data/perspective/client/Ignition_nube)
