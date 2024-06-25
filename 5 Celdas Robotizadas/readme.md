* DISCLAIMER: para poder instalar y correr la estacion se necesita com minimo la version 2024 de robotstudio con licencia y el palletizing powerpac que se puede encontrar en la pagina de ABB y el IRC5 OPC server cofigurator
# Propuesta de Celdas Robotizadas
Para el proyecto, se tiene contemplado emplear una celda robotizada para el paletizado de las cajas de baldosas. Esta celda empleará un gantry robotizado que permita recoger y apilar las cajas en la distrubución adecuada para su despacho, sobre AGVs que lleven cada cargamento hasta la bodega o su transporte de salida de la planta. Se tendrán AGVs en constante movimiento para poder disponer de todas las cajas de manera adecuada. Se plantea simular el gantry por medio de RobotStudio, y realizar su operación y control empleando un controlador IRC5. 

## Proceso de creación de la celda

Se inicia con la siguiente hoja de ruta para la creación de la celda.


![celda robotica-Página-4 drawio](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/636d961a-63b0-476f-8dbf-573a20922914)




## Propuesta de distribución de celda


![celda robotica-Página-12 drawio](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/63dbf713-ce92-4b40-bd00-65adbe63fc43)



Se define el WS1 como la banda transportadora, el WS2 como las estibas donde se colocaran las cajas y el WS3 son las rutas donde transitaran los agvs


## Analisis de riesgos

Para la implementacion de la celda se identificaron las siguientes fuentes de riesgo

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/c8d748d5-91f3-40f4-aa44-31be357bc690)

Luego de esto se desarrollo la matriz de riesgos de riesgos comparando antes y despues de siguiendo la IEC62061

### Matriz de riesgos previa

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/3c26620c-d0d9-4b87-8b96-0fdc5bdf0467)

### Mitigación de riesgos

Se planean implementar las siguientes acciones para la mitigación de riesgos

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/89b32b6e-d960-40fd-a15c-89b3a7084761)
![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/14a0c63f-e5af-4664-b72b-1305ad81cb29)

### Matriz de riesgos posterior

Luego de aplicar las mitigaciones de riesgos se obtuvo la nueva matriz de riesgos

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/82dbcedf-9d7a-4ad7-b074-573d78a604ef)


### Comparación

Por ultimo se realiza la comparaci'on de las clasificaciones de riesgo, se pueden ver disminuciones significativas.

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/3f857d22-3046-4d04-b3e3-3ff999d0c0ff)



## Plano de planta
Luego de las consideraciones de seguridad, se obtiene el siguiente plano de planta.

![Celda robotica plano](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/3f03b6f2-6cc8-4ec6-8659-2c04832ef531)



## AMR

Para los AMR se opto por los AMR F702 de ABB que se pueden ver en la imagen

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/74e5ea6f-0bf3-49ad-b862-ac5aff12336b)


![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/dbee8790-6676-4727-88b7-8d63c8a24ccf)



Estos robots cuentan con protección de 360°. Ademassoprtan cargas de 2000 kg a una altura 0 y cargas de 1183 kg a una altura de 6m


## Proceso de creación del robot Gantry de XYZ

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


## Smart Components

### Banda transportadora

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



### Paletizado


Primero se le dio a las estibas la propiedad fisica fixed para qe se mantengan en una posición y tengan collisiones con las cajas.
luego se creo el smart component donde se agragaron bloques attacher, dettacher, positioner, line sensor, timer queue, compuerta not y el primer smart component que creamos llamado SmartComponente_2.


![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/665e7fcc-5c9a-4e23-b9d5-36321cf7dab7)
![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/759e2b87-0f4d-412f-a1c2-9fd8b059d86d)

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/f314229e-f40c-41be-a821-527d8b33e2cb)


En un primer momento se intento utilizar los bloques attacher y detacher, pero esto cargaba demasiado la simulacion y no era posible hacer una visualización correcta, por eso se cambio el sistema y en la imagen se puede ver como estos bloques no estan conectados a nada en la estación, entonces se opto por ua logica diferente que explicaremos a continuacion.


Primero tenemos 3 entradas digitales que son DI_attach, que le va a decir al SmartComponent (SC) cuando mover la caja, luego tendremos, el crear caja conectada al SC2 denuevo por si se requiere usarlo en codigo, borrar_caja que se utilizara para borrar un lote completo de cajas cuando se quiere empezar el siguiente y tenemos 3 salidas digitales, Atached que nos confirmara que la caja ya se movio, detached, que se usaria y estuvieramos usando los bloques attacher y detacher, y sensor banda que viene del SC2 que nos dice si tenemos una caja en el borde.

En la logica comenzamos asumiendo que ya tenemos una caja en el borde entonces cuando elgantry este en la posicion donde puede agarrar la caja esto va a activar el line sensor que como se puede ver va esta unido al gripper.

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/3ce321c5-c6e2-457e-9baa-8bd1fcd50a85)

Al activarse este line sensor va a activar la señal DI_Attach, suponiendo que vamos a agarrar la caja, tambien va a poner la caja en una cola donde va a ser el unico elemento por lo que sera el back y el front a la vez, despues de esto el gantry se va a mover a la posicion donde deberia dejar la caja, en esa posicion se va a desactivar la señal DI_Attach, que al pasar por la compuerta not se va a invertir, esto va a activar un positioner que como objeto a posicionar va a tener el frente de la cola, que es la caja que queremos mover, y ademas va a activar un timer que despues de 0.5 segundos va a desencolar la caja de la cola dejandola vacia, este timer es necesario ya que si mandabamos la señal de desencolar al mismo tiemo que el positioner, no este ultimo perdia la referencia antes de poder moverla, y cuando se ejecute activa la salida attached para que el gantry sepa que ya dejo la caja y pueda ir a la siguiente.

El positioner al activarse ponen en un segunda cola la caja que posiciono, esta cola va a guardar todas las cajas del lote de tal manera que cuando activemos la señal borrar caja se van a borrar todas las cajas del lote actual y podamos continuar con el siguiente. 

#### Logica de estación

Por ultimo nos vamos a la logica de estación

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/ed1f3229-c012-4332-ae20-671b09c2f40b)

Donde conectaremos las entradas y salidas del SC a salidas y entradas del controlador

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/a309531f-9f30-46fa-ab16-aa5170bce2b4)

#### Simulación con SC



https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/c47f2851-4832-48b7-b615-857ed4c6d2d0


## AGV 
para la simulación del AGV se decidio tomar un enfoque similara a los SC, donde se va a generar un modelo 3d del gantry y se va a tratar como un solo solido el gantry y la estiba que lleva, y se usara un camino como banda transportadora, para simular el movimiento del AGV, se colocaria en el camino y se le dara velocidad a la superficie simulando el movimiento.

Se empieza denuevo con el modelo 3D del AGV.


![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/532ca3ed-fb99-4bc1-947b-b227191e1dd7)

Las medidas vienen de las imagenes que se ven arriba para el bloque del AGV y el tamaño de las estibas es el mismo de los diseños 3d que vienen incluidos en robotstudio. El diseño no es tan detallado ya que lo que necesitamos es entender los espacios de trabajo de la celda.
Luego en robot studio se genera el camino con solo 10mm de alto para que interfiera lo menos posible con el proceso luego a este objeto le habilitamos la velocidad superficial para poder moverlo. 

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/d6c3bac3-0e7a-44bb-9e45-c7bc7c7c7bb3)

Luego importamos el AGV y lo ubicamos donde seria el punto de partida.

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/acc2b143-839c-49c2-a1b8-eca4f41dade0)

Con esto, procedemos a crear un nuevo SC. Para este SC vamos a usar los bloques PhysicsControl, Source, QUEUE y line sensor.

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/21d16369-a560-49b3-8333-b6a266d0dcf8)


Primero vamos a ubicar el line sensor, en una posición donde podamos deducir que el agv ya esta listo para ser usado.

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/d4060b3b-6032-49f5-ac5d-bbcec1c1352e)

Luego vamos a generar la logica.

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/43d4005c-d6d1-4893-a120-8f52cbb4a4c3)


Vamos a tener 3 entradas digitales que como sus nombres lo indican se van a encargar de prender y apagar la banda, crear y borrar los agv y se tiene una salida digital que nos va a indicar cuando el AGV este en posicion. El sensor de linea solo esta conectado a la salida digital.

La entrada digital controla el bloque de physics control, para darle o quitarle la velocidad al camino, se escogio una velocidad de 1 m/s ya que esta dentro del rango que nos daba el datasheet del agv.

Despues se conecta la entrada crear agv con el bloque source, y cuando este bloque es ejecutado pone al final de la cola el agv que se acabo de crear.

Por ultimo la entrada borrar AGV se conecta con la opcion Delete del bloque queue que borra el frente de la cola que en este caso seria el AGV que hallamos creado hace mas tiempo.

Despues se crean las señales en el controlador y se conectan al SC.

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/057eb382-8f9b-4ddf-b033-70708d85b9ea)

Por ultimo se cre la logica del Rapid, donde se tiene el paletizado y al acabar un paletizado, se crea un nuevo AGV, despues se prende la banda y se espera que el sensor de linea se desactiva implicando que el AGV en el que ya se paletizo, ya salio y despues se espero que se vuelva a activar el sensor implicando que el nuevo AGV ya esta en posicion, cuando ya esta en posicion el nuevo AGV se apaga la velocidad del camino, y se borra el AGV, y las cajas que ya fueron paletizadas y se vuelve a iniciar el ciclo.

![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/b7974f69-edbb-4f02-88c5-0e458b461b18)

## Simulación celda gantry+AGV


https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/22f66701-7e49-45cc-879f-7aad3a6c8b94



## Seguridad con el codigo

Dentro de las condiciones de seguridad se integro una interrupción dentro del codigo RAPID, esta interrupcion se anclo a la entrada digital que simula las cortinas laser, por lo que cuando esta entrada se active hara que el robot pare y se necesitara que se apage la salida y que se oprima el boton safe para que el boton continue su funcionamiento normal.

### Simulación interrupción


https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/fad1a634-4b4d-4bed-81ab-7fb4522a86ef



## conexión con ignition
Primero se debe descargar la aplicación ABB IRC5 OPC server
Para la creación de tags en ignition se encontraron dos maneras posibles, la primera es que las entradas y salidas que se definan en el controlador ya crearan sus tags en el servidor OPC y la segunda es declarando variables de rapid como PERS lo que hara que se generen los tags de las mismas, con todo esto se tiene el siguiente resultado de la conexion entre ignition y la celda robotica




https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/af416179-0bd2-4a48-af30-2b0894701d8e




## Robotstudio AR


Por ultimo, ya que queriamos poder ver como se veria la celda robotica en tamaño real, y para que el cliente pudiera ver un aproximado de como se veria si la instala en su planta, decidimos utilizar la realidad aumentada que nos proporciona robot studio, para esto descargamos la aplicación robotstudio AR viewer en un smartphone.


![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/9cf92361-d706-405e-bddb-16a12678b3f3)


Luego de esto grabamos la simulación con el boton export viewer en robotstudio.


![image](https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/72305e47-23af-438f-af11-3e870901aa86)


Con esto se genera un archivo .glb que luego se puede descargar desde drive en la app y se puede cargar la simulacion para verla, ya sea a escala real o disminuida en realidad aumentada.

### Simulación AR



https://github.com/danielCamiloP/TecnomecatroniX/assets/62917958/63ebebda-f077-451e-a8d8-d1ad8605087f



