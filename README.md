## laboratorio 06 - Diseño de banco de Registro

### Integrantes:

#### Pedro Javier Puerto Joya
#### Esteban Suarez
#### Jorge Sanchez

## Introducción

sadsadad
Para este paquete de trabajo, deben estar inscrito en un grupo y clonar la información del siguiente link [WP06](https://classroom.github.com/g/XHLhUCe3). Una vez aceptado el repositorio debe descargarlo en su computador, para ello debe clonar el mismo. Si no sabe cómo hacerlo revise la metodología de trabajo, donde se explica el proceso

Las documentación deben estar diligencia en el archivo README.md del repositorio clonado.

Una vez clone el repositorio, realice lo siguiente:


## Descripción 
Se debe diseñar un banco de registro tal que:

* El banco de registro debe tener 16 registros de R/W.
* Permitir la lectura de 2 registros  simultáneamente 
* Permitir la escritura  de 1 registro, acorde a la señal de control regwrite
* Contar con señal de rst, la cual  ponga  todos los registros en un valor conocido.

![cn](https://github.com/Fabeltranm/SPARTAN6-ATMEGA-MAX5864/blob/master/lab/lab07-BancosRgistro/doc/caja%20negra.png)

* Visualizar la información, en al menos dos display de 7 segmentos (información de cada registro leído).
* El ingreso de la información se debe hacer por medio de los interruptores.


**Opcional. Da mas puntos:**
* Parametrizar el tamaño de palabra de cada registro  y la cantidad de registro ( Por defecto =4 bits). Se recomienda leer el documento de este [link](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-884-complex-digital-systems-spring-2005/related-resources/parameter_models.pdf) .
* Pre cargar el banco de registro con información.  _Usar $readmenh_  (Investigar: "Initialize Memory in Verilog").

Entregables:

* Documentación
* Archivo `testbench` el cuál debe simular la escritura de 16 registros y 8 lecturas mas el rst, el resultado de la simulación debe visualizarse en diagrama de tiempo.
* Vídeo de la implementación.
* Código HDL de la solución.
.

 ![caja](https://github.com/Fabeltranm/SPARTAN6-ATMEGA-MAX5864/blob/master/lab/lab07-BancosRgistro/doc/banco%20registro.png)

## Desarrollo de la practica

#### Descripción
Por medio de los conceptos recibidos en el contenido de la tematica tratada durante las sesiones de clase se procede a realizar un desarrollo con bancos de registros, en donde se tiene el control de los saltos mediante registros de entrada de 2bits y 4 bits como son:
####	reg [1:0] addrRa; lectura
####    reg [1:0] addrRb; lectura
####	reg [3:0] addrW;  Escritura
####	reg [3:0] datW;   Escritura

#### addrRa y addrRb son los registros que permiten seleccionar la posición del banco de registros que se desea visualizar en las salidas denominadas datOutRa y datOutRb  , en este caso las posiciones de registros se observan de la siguiente manera:

## Entradas 
#### breg[0] <= 9;  //  1001 
#### breg[1] <= 7;  //  0111
#### breg[2] <= 5;  //  0101
#### breg[3] <= 1;  //  0001
		
## Salidas
#### datOutRa
#### datOutRb

#### En las diferentes posiciones de entrada del banco de registros se encuentran cargados por defecto valores como son 9"1001", 7 "0111",5 "0101",1 "0001". asi.
