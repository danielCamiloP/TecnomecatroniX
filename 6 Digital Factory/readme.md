

# Fábrica Digital

Para crear el gemelo digital de la planta de producción de cerámica se modeló el CAD de las siguientes máquinas:

- Prensa: SACMI PH1500
- Volteadora de baldosas: SACMI RPR900
- Secadora: SACMI EVA 992
- Esmaltadora y Engobe: CAM 1804
- Decoradora: DDG 1422
- Empaquetadora: SACMI DINAMICA EKOROLL

Posteriormente se exportaron los archivos CAD al programa Siemens NX Mechatronics Concept Designer donde se crearon las físicas de lás correspondientes máquinas.

## Prensa

La prensa cuenta con un mecanismo prismático para llenar el molde con el polvo procesado en las etapas anteriores de la planta, para eso se crearon dos Sliding Joints.
![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/73075254/d41a6329-fefc-4966-bde2-5689aa1c6579)

Se modelaron también el cilindro principal que ejerce la acción de presión y un actuador en el molde que sube las baldosas una vez son prensadas para que puedan ser expulsadas de la prensa.
![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/73075254/a887543e-7403-40ec-a602-e01486705b83)

La mísma bandeja que se encarga de rellenar el molde, expulsa las baldosas ya prensadas y presentes en el molde, para modelar este componente se usó también una Sliding Joint.
![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/73075254/22c20644-6fc1-44f3-9305-a0c77dea9b5f)

## Volteadora de Baldosas

La volteadora cuenta con dos bandas transportadoras de rodillos, una de entrada y otra de salida, y el Tipper a su vez se modela como dos bandas de rodillos enfrentadas y conectadas a una junta prismática para tomar las baldosas cuando llegan a la posición de volteo. Se modelaron dos sensores a los extremos del tipper para detectar las baldosas en ambos sentidos. El Tipper está conectado a un motor que gira continuamente en el mismo sentido.
![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/73075254/e76ea360-8dd3-4b8f-a5fb-99e8984c431b)


## Sistema de bifurcación


Se diseñó una lógica para el sistema de bifurcación, el cuál está asociado a un código en grafcet, las baldosas toman un camino según un bit lógico (SelP), de esta manera, van a la dirección deseada y la banda anterior espera a que la banda de bifurcación esté desocupada para continuar el flujo de baldosas.

![bifurcacion](https://github.com/danielCamiloP/TecnomecatroniX/assets/52110700/d86ab048-e153-4638-915d-e77cfc4fb3ed)

## Secadora

Se modela un sistema de secado como una caja, en la que entran las baldosas y salen con una velocidad constante.
![Captura de pantalla 2024-05-29 135722](https://github.com/danielCamiloP/TecnomecatroniX/assets/52110700/75f57c09-3654-448f-8615-1afe33b354cc)

## Esmaltadora y Engobe

Se crea el efecto de cambio de aspecto para la esmaltadora y el engobe en cada camino.
![engobe](https://github.com/danielCamiloP/TecnomecatroniX/assets/52110700/7a341ae7-3091-4b5d-b8a9-9e9c9fc792e7)
## Decoradora

Se modela la decoradora como el funcionamiento que se ve en el video de SACMI. Las baldosas entran y la banda no se detiene.
![deco](https://github.com/danielCamiloP/TecnomecatroniX/assets/52110700/042b0fb5-9572-44d7-92c0-e201232fff79)

## Empaquetadora

Para modelar la empaquetadora primero se creó la simulación de los rieles en C, donde el gripper sigue la trayectoria de los rieles y cuenta con dos densores de colisión para detectar cuando el gripper llega a ambos extremos del riel. Además el gripper tiene una junta prismática y un sensor de colisión para agarrar los objetos que detecte.

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/73075254/6fa94ed1-4d10-414e-b60b-77c8a007234e)

Posteriormente se importó estqa parte en el ensamble global. Donde se modelaron todas las físicas de la empaquetadora.

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/73075254/7e474bf2-5804-4a4e-8123-5ed7e8a47ebc)


