* DISCLAIMER: para poder instalar y correr la estacion se necesita com minimo la version 2024 de robotstudio con licencia y el palletizing powerpac que se puede encontrar en la pagina de ABB
# Propuesta de Celdas Robotizadas
Para el proyecto, se tiene contemplado emplear una celda robotizada para el paletizado de las cajas de baldosas. Esta celda empleará un gantry robotizado que permita recoger y apilar las cajas en la distrubución adecuada para su despacho, sobre AGVs que lleven cada cargamento hasta la bodega o su transporte de salida de la planta. Se tendrán AGVs en constante movimiento para poder disponer de todas las cajas de manera adecuada. Se plantea simular el gantry por medio de RobotStudio, y realizar su operación y control empleando un controlador IRC5. 

## proceso de creación de la celda

Se inicia con la siguiente hoja de ruta para la creación de la celda.


![celda robotica-Página-4 drawio](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/636d961a-63b0-476f-8dbf-573a20922914)





## Propuesta de distribución de celda


![celda robotica-Página-12 drawio](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/63dbf713-ce92-4b40-bd00-65adbe63fc43)



Se define el WS1 como la banda transportadora, el WS2 como las estibas donde se colocaran las cajas y el WS3 son las rutas donde transitaran los agvs


## Elementos de seguridad a considerar
Como primera medida, se considerarán cortinas láser para evitar el ingreso de personal al área de trabajo mientras se encuentre en operación el sistema. Adicionalmente se considerarán alarmas y luces indicativas para señalizar el estado del proceso, teniendo en cuenta los estados de parada, alistamiento, ejecución, y falla. 
Con esto se genera el siguiente plano de planta de la celda robotica:

![Celda robotica plano](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/3f03b6f2-6cc8-4ec6-8659-2c04832ef531)



## AGV

Para los AGV se opto por los AMR F702 de ABB que se pueden ver en la imagen

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/74e5ea6f-0bf3-49ad-b862-ac5aff12336b)


![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/dbee8790-6676-4727-88b7-8d63c8a24ccf)



Estos robots cuentan con proteccion de 360°. Ademassoprtan cargas de 2000 kg a una altura 0 y cargas de 1183 kg a una altura de 6m


## Proceso de creacion del robot Gantry de XYZ

Se planea utilizar en la celda un robot gantry IRB 8400/FP

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/acbce1c0-c7bc-45eb-ad07-2ecc29195a51)


Para poder simular el proceso con el robot gantry se necesito crear un robot desde cero ya que ABB no cuenta con las bibliotecas de estos robots incluidas en robotstudio para su simulación.
Con este fin, se empezo por el modelado 3d del robot 


![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/79ea9017-039b-47f1-aa5b-3d64e2666bef)


Luego de esto se importo en robot studio en formato .SAT y se procedio en la opción crear nuevo mecanismo.


![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/812fab56-814e-4ec7-962a-346142fa65ae)

Ahi se definieron los eslabones, articulaciones, limites del robot y marco de referencia del efector final.


![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/db8c2fcb-99ae-419d-94f3-831ed4ce755c)

Con el robot ya creado ahora era necesario poder controlarlo, ya que este robot no era una libreria propia de robotstudio, no tenia controladores compatibles por lo que se tenia que crear un controlador nuevo para esto se descargo el Add-in de robotstudio Stand-Alone Controller donde podemos crear nuestros propios controladores para los robots que nosotros mismos hagamos.


![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/d46113db-bf2c-430e-aff6-99832dae186a)


Luego de descargar el Add-in nos vamos al installation manager para crear un nuevo controlador.
![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/6812c03a-951e-423e-b207-91c9e7171697)


Y desde aqui creamos un nuevo controlador


![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/cddee13a-b781-4638-ab46-d97b75a9158b)


Despues añadimos Robotware y el SAC.


![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/31e899f5-3684-4877-a88f-a089c528ba7d)


Y en la siguiente ventana escogemos el tipo de robot que queremos controlar, en este caso seria un GANTRY XYZ, y ya podemos crear nuestro controlador.



![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/c01383a7-5be6-450f-bffc-83aab60ca518)


Despues solo necesitamos ir a la ventana controller y añadir el controlador que creamos en la estacion


![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/247ac702-1636-4db2-8320-e950506c05c0)


Y ya tenemos nuestro nuevo robot gantry en robotstudio.


## Resultado simulación gantry 


[//]: <> (https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/44545cdb-1ea5-4128-8c42-93de2d60c29e)


https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/0516503f-843f-4945-8509-8554538535a9

Luego de tener el robot procedemos a implementar el diseño de la celda que vimos anteriormente, para esto instalamos el Add-in Equipment builder


![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/0628575e-72df-41dc-9653-fecb4de253dc)


Con este paquete podemos incluir las bandas transportadoras que son el WS1 asi como las estibas que son el WS2.i, asi como podemos incluir diferentes medidas de seguridad como las barreras solidas, las barreras laser y los botones de parado de emergencia.

Luego instalando el power pack de paletizado que se descarga desde la pagina de ABB podemos conseguir el gripper que escogimos


![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/eab84d0f-6786-4741-a699-f5150ae50eb6)


A continuación se puede observar el gantry con las medidas de seguridad iniciales, el gripper, las estibas y las bandas transportadoras

https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/c10ecb70-2565-4b6f-831e-829b46f93bb0


## smart components

### banda transportadora
Se empezo por realizar el smart component de la celda transportadora para esto se selecciono el modelo CAD de la banda transportadora que se muestra a continuación


![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/b262e9ec-ad0a-483b-9df5-6ce92351fdf0)


Despues se le dio dio un comportamiento fisico habilitando la velocidad superficial


![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/a1484cd4-3e75-48bf-a1da-fd308fe0f117)

Luego de esto se le creo una caja con el modelado 3d propio de robotstudio y se ubico al inicio de la banda transportadora.


![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/4f87e8df-7f6e-4ace-81ec-405538531bbf)


Ya teniendo los elementos procedemos a crear el smart component, para esto se usaron bloques source, sink, physics control, line sensor, timer, una compuerta not y los dos modelos CAD

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/1b631da6-fc11-4905-9f19-aa825b542c7c)

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/ed56d64e-84ee-4e31-8c3c-4423ab42a2b2)


#### Logica smart component


![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/bb03bcde-f07a-4e71-ab9c-f2bc14214475)


Ahora vamos a explicar la logica del smart component que pueden ver arriba.
Primero se ubico el bloque source y sink que en un principio estaban conectados a las entradas crear y borrar caja, estas entradas estan ahi en caso que se quieran quitar las cajas por medio de codigo o para hacer pruebas, en la configuracion del source se eligio que el elemento generado fuera la caja, que el transiente fuera verdadero para que al acabar la simulación se borren todas las cajas generadas y se definio un comportamiento dinamico para que se pudieran mover con la cinta transportadora
Luego se ubico el sensor de linea al final de la banda transportadora, este sensor como se puede ver esta conectado a una salida digital que nos sirve para saber si tenemos una caja en el borde

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/6ce3dadf-d069-4f55-a12b-916de8183e68)


Como se puede ver el sensor esta conectado a una compuerta not para que cuando se active, osea que exista una caja en el borde, la compuerta mande un 0 lo que desactiva el movimiento de la cinta transportadora, la salida de esa compuerta not también va hacia un timer que emite un pulso cada 1.5 segundos que esta conectado al source, con esto se logra generar cajas de manera equidistante, y solo cuando no se tengan cajas en el borde.



### paletizado


Primero se le dio a las estibas la propiedad fisica fixed para qe se mantengan en una posición y tengan collisiones con las cajas.
luego se creo el smart component donde se agragaron bloques attacher, dettacher, positioner, line sensor, timer queue, compuerta not y el primer smart component que creamos llamado SmartComponente_2



## conexión con ignition


## Robotstudio AR


Por ultimo, ya que queriamos poder ver como se veria la celda robotica en tamaño real, y para que el cliente pudiera ver un aproximado de como se veria si la instala en su planta, decidimos utilizar la realidad aumentada que nos proporciona robot studio, para esto descargamos la aplicación robotstudio AR viewer en un smartphone.


![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/9cf92361-d706-405e-bddb-16a12678b3f3)


Luego de esto grabamos la simulación con el boton export viewer en robotstudio.


![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/72305e47-23af-438f-af11-3e870901aa86)


Con esto se genera un archivo .glb que luego se puede descargar desde drive en la app y se puede cargar la simulacion para verla, ya sea a escala real o disminuida en realidad aumentada.
