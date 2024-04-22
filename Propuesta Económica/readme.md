# Evaluación económica del proyecto

Se estudiará económicamente la viabilidad de este proyecto, para esto, se estimará la inversión inicial que se requiere en máquinas suponiendo que todas las máquinas se compran en el mes 0.

## Estimado de la inversión inicial por sistema

### Celda Robótica:

- **Robot:** US$25.000 a US$200.000 o más
- **Periféricos:** US$10.000 a US$50.000
- **Software:** US$5.000 a US$20.000
- **Integración:** US$10.000 a US$50.000
- **Total:** US$50.000 a US$320.000 o más

### Sistema SCADA:

- **Hardware:** US$5.000 a US$25.000
- **Software:** US$1.000 a US$10.000
- **Ingeniería e integración:** US$10.000 a US$50.000
- **Total:** US$16.000 a US$85.000

### Red de Comunicaciones:

- **Componentes de red:** US$500 a US$5.000
- **Ingeniería e integración:** US$2.000 a US$5.000
- **Total:** US$700 a US$10.000

### Nuevas máquinas

- **Nuevas decoradoras, bandas transportadoras y demás elementos de la planta**: US$500.000

### Total general estimado: US$1.000.000 

Se establece finalmente un valor de US$1.000.000 que corresponde a COP$4.000.000.000 aproximadamente de inversión inicial.

## Nómina para el proyecto

Este proyecto contará con los 7 ingenieros que conforman este grupo. Se asigna un salario de COP$8.000.000 mensuales por ingeniero, dado que son 7 ingenieros esto sería (mensual):

$$
S =  $8.000.000*7 = $56.000.000
$$

También se requiere mano de obra que cumpla la función de instalar, mover y transportar los diferentes equipos, para ellos se establece un salario promedio de $2.054.520 y se estima la contratación de 50 personas en este año de implementación del proyecto. Entonces el costo mensual de nómina por esta mano de obra es:

$$
S =  $2.054.520*50 = $102.726.000
$$

El costo total de la nómina mensual sería:

$$
C_{nom} =   $102.726.000 +  $56.000.000 = $158.726.000
$$

Lo que corresponde a  $1.904.712.000 de costos de nómina a lo largo de todo el año (12 meses).

La inversión total por el proyecto contando la inversión en máquinas y mano de obra corresponde a $5.904.712.000 (Año 0).

# Puesta en marcha

Ahora se calcularán los flujos de caja cuando la implementación haya acabado y esté puesta en marcha.

# Productos 

Según los productos definidos, se toman 3 referencias de estos en páginas del mercado para tener datos de precio, tamaño de lote, entre otros importantes para analizar económicamente el proyecto. Primero, se definirán los ingresos por ventas de cada producto según la productividad obtenida de las simulaciones.

## Producto 1 - Baldosa mate 30x60 cm

![image](https://github.com/danielCamiloP/TecnomecatroniX/blob/main/Propuesta%20Econ%C3%B3mica/imagenes/prod2.png)

La referencia de este producto puede ser encontrada en este [enlace](https://www.homecenter.com.co/homecenter-co/product/395624/piso-pared-ceramico-avellano-beige-30x60cm-caja-162-m2/395624/?kid=goosho_1246419&shop=googleShopping&gad_source=1&gclid=CjwKCAjwz42xBhB9EiwA48pT7zUZUM5bbt577Q1XyNc6PeTEHuW5_orI4zHAUkWnBT5m6q9_t3lo5BoCgkIQAvD_BwE).

Esta tiene un precio por metro cuadrado de $41300. De la ficha técnica de este producto y de los resultados de la simulación, se obtienen los resultados mostrados en la siguiente tabla.

| Variable               | Valor         |
|------------------------|---------------|
| Tamaño lote (m^2)      |          1,62 |
| m^2 producidos         |     30.000,00 |
| Lotes producidos       |     18.518,52 |
| Precio de un lote      |       $66.906 |
| Lotes vendidos al mes  |   14814,81481 |
| Total ganancia mensual |  $991.200.000 |

Se establece un aproximado de lotes vendidos, donde este valor corresponde al 80% de lotes producidos. Todos esos datos son mensuales.

## Producto 2 - Baldosa esmaltada decorada 30x60 cm

![image](https://github.com/danielCamiloP/TecnomecatroniX/blob/main/Propuesta%20Econ%C3%B3mica/imagenes/prod3.png)

La referencia de este producto puede ser encontrada en este [enlace](https://www.decorceramica.com/atelier-b-30-60-marengo-kc03me182/p).

Esta tiene un precio por metro cuadrado de $79519. De la ficha técnica de este producto y de los resultados de la simulación, se obtienen los resultados mostrados en la siguiente tabla.

| Variable               | Valor           |
|------------------------|-----------------|
| Tamaño lote (m^2)      |            1,44 |
| m^2 producidos         |       30.000,00 |
| Lotes producidos       |       20.833,33 |
| Precio de un lote      |        $114.507 |
| Lotes vendidos al mes  |     16666,66667 |
| Total ganancia mensual |  $1.908.456.000 |

## Producto 3 - Baldosa texturizada 30x60 cm

![image](https://github.com/danielCamiloP/TecnomecatroniX/blob/main/Propuesta%20Econ%C3%B3mica/imagenes/prod1.png)

La referencia de este producto puede ser encontrada en este [enlace](https://corona.co/productos/revestimientos/paredes/pared-santa-maria/p/451419791).

Esta tiene un precio por metro cuadrado de $38300. De la ficha técnica de este producto y de los resultados de la simulación, se obtienen los resultados mostrados en la siguiente tabla.


| Variable               | Valor         |
|------------------------|---------------|
| Tamaño lote (m^2)      |          1,89 |
| m^2 producidos         |     15.000,00 |
| Lotes producidos       |      7.936,51 |
| Precio de un lote      |       $72.387 |
| Lotes vendidos al mes  |   6349,206349 |
| Total ganancia mensual |  $459.600.000 |

## Resumen de los productos

La siguiente tabla resume la información de ganancias de cada producto

| Producto | Mensual         | Anual            | % participación |
|----------|-----------------|------------------|-----------------|
|        1 |    $991.200.000 |  $11.894.400.000 |          29,51% |
|        2 |  $1.908.456.000 |  $22.901.472.000 |          56,81% |
|        3 |    $459.600.000 |   $5.515.200.000 |          13,68% |
| Total    |  $3.359.256.000 |  $40.311.072.000 |         100,00% |

Con esto, se establece un total de ventas de $40.311.072.000 anuales, se establece una tasa de crecimiento de ventas del 10% anual.

# Costos

## Materia prima

Debido al aumento esperado en la producción, se deberá adquirir más materia prima cuando la nueva planta esté puesta en marcha. Para esto se calcula la productividad de la planta actual y de la automatizada, obteniendo como resultado un aumento de 67262.4 m² mensuales. A partir de este dato, se estima que el costo de producir 1m² en materia prima es de $20000, por lo que mensualmente se obtiene que los costos de materias primas serían:

$$
C = $20000*67262.4 = $1.348.248.000
$$

Anualmente, serían $16.142.976.000 y se toma una tasa de aumento de precio del 10% anual.

## Costos de operación

Debido a que no se han definido máquinas aún, se toma como referencia el estado de resultados de la empresa Corona para el año 2021/2022 ilustrado en la siguiente imagen.


Se observa que los costos operacionales es el 55% del valor de las ventas, se toma entonces este valor para hacer un estimado de los costos operacionales obteniendo:

$$
C_{op} =  $40.311.072.000*0.55 = $22.171.089.600
$$

## Costos de nómina

De los VSM establecidos, se construyen las siguientes tablas que ilustran la cantidad de personal en cada etapa del proceso, para la planta actual se tiene un salario de MXN$300 diarios (datos de la empresa Castel) lo cual corresponde mensualmente a COP$2.054.520,00, en la planta actual, los costos de nómina se representan en la siguiente tabla:

| Proceso    | Cantidad de personal | Salario          |
|------------|----------------------|------------------|
| Prensado   |                    9 |   $18.490.680,00 |
| Esmaltado  |                    3 |    $6.163.560,00 |
| Impresión  |                    3 |    $6.163.560,00 |
| Horneado   |                    3 |    $6.163.560,00 |
| QC         |                    9 |   $18.490.680,00 |
| Empacado   |                   27 |   $55.472.040,00 |
| Paletizado |                   27 |   $55.472.040,00 |
| Total      |                    = |  $166.416.120,00 |

Para la planta automatizada, se tiene que:

| Proceso          | Cantidad de personal | Salario         |
|------------------|----------------------|-----------------|
| Prensado         |                    9 |  $18.490.680,00 |
| Esmaltado+Engobe |                    6 |  $12.327.120,00 |
| Impresión        |                    3 |   $6.163.560,00 |
| Horneado         |                    3 |   $6.163.560,00 |
| QC               |                    3 |   $6.163.560,00 |
| Empacado         |                    3 |   $6.163.560,00 |
| Paletizado       |                    3 |   $6.163.560,00 |
| Total            |                    = |  $61.635.600,00 |

Como se observa, los costos de nómina se ven reducidos, lo cual representa un ahorro que equivale a:

$$
C_{nom} = $166.416.120,00 - $61.635.600,00 = $104.780.520,00
$$

Anualmente equivale a COP$1.257.366.240, los salarios de los empleados aumentan el 10% cada año, por lo que este ahorro se verá reducido con el paso del tiempo.
