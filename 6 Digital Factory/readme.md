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

