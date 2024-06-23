# Industria 4.0 y transformación Digital

## Arquitectura del proyecto
Como parte del proyecto, nuestro equipo aspira poder realizar una integración directa con las ventas realizadas a nuestros clientes, y nuestra línea de producción, permitiendo agregar valor por medio de cerámica personalizada con un patrón que pueda formarse empleando varias baldosas. Este servicio busca innovar en la industria cerámica aprovechando las tecnologías de impresión con tintas Kerajet que podrían facilitar emplear diseños de nuestros clientes a nuestra planta de producción. Para ello, hemos planteado la siguiente arquitectura de comunicaciones: 

![ArquitecturaOld](https://github.com/danielCamiloP/TecnomecatroniX/assets/37418973/d0081edc-f16b-4427-be46-f959848d6143)

Es importante aclarar que conforme avance el proyecto, se ajustará el diagrama de arquitectura acorde a los cambios que sean necesarios para implementar toda la arquitectura. Dicho esto, esta estructura de Industria 4.0 es apenas un borrador de lo que se planea hacer con el proyecto.

Posteriormente en el desarrollo del proyecto, fue necesario que emplearamos un servidor OPC DA en vez de uno OPC UA. Al añadir la arquitectura de nivel de campo, se presenta a continuación la arquitectura modificada para el proyecto:
![Arquitectura](https://github.com/danielCamiloP/TecnomecatroniX/assets/37418973/b997286d-a4c8-4f11-b336-13288915515d)


## Propuesta de transformación digital:
Para el proyecto, se optó por usar un enfoque de datos para la propuesta de transformación digital, permitiendo recolectar datos de producción desde los controladores de los equipos, y así poder realizar ajustes a la producción basados en datos actualizados de producción. Si se considerara el número de baldosas producidas por minuto, ya se tendría como obtener los KPI de planta desde un manejo de bases de datos, sin necesidad de implementar IoT de una manera forzada dentro de la planta.

Como grupo, consideramos que mucho de lo que se entiende como transformación digital, se reduce a poder manipular líneas de producción desde un lugar remoto, como por ejemplo poder encender o apagar un motor a través de un chat de telegram. Una verdadera propuesta de valor puede venir simplemente de mejorar los procesos de planta con datos más actualizados.

Otra manera en que podemos emplear una transformación digital dentro del proyecto, es implementando tecnologías recientes como lo son la realidad aumentada, la cual nos permite mostrar de una manera mucho más llamativa el proyecto, empleando herramientas como "RobotStrudio AR Viewer", la cual nos permite presentar la línea de paletizado desde una perspectiva más entendible. A futuro esto podría también usarse para entrenamiento y reconocimiento de la planta en un entorno mucho más seguro y sin interrumpir el funcionamiento de la misma para tareas de formación y entrenamiento de nuevos operarios.

La implementación de la realidad aumentada puede observarse en la página de [Celdas robotizadas](https://github.com/danielCamiloP/TecnomecatroniX/tree/main/5%20Celdas%20Robotizadas) de este repostorio.
