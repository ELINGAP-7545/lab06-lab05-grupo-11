## laboratorio 06 - DiseÃ±o de banco de Registro

### Integrantes:

#### Pedro Javier Puerto Joya
#### Esteban Suarez
#### Jorge Sanchez

## IntroducciÃ³n

sadsadad
Para este paquete de trabajo, deben estar inscrito en un grupo y clonar la informaciÃ³n del siguiente link [WP06](https://classroom.github.com/g/XHLhUCe3). Una vez aceptado el repositorio debe descargarlo en su computador, para ello debe clonar el mismo. Si no sabe cÃ³mo hacerlo revise la metodologÃ­a de trabajo, donde se explica el proceso

Las documentaciÃ³n deben estar diligencia en el archivo README.md del repositorio clonado.

Una vez clone el repositorio, realice lo siguiente:


## DescripciÃ³n 
Se debe diseÃ±ar un banco de registro tal que:

* El banco de registro debe tener 16 registros de R/W.
* Permitir la lectura de 2 registros  simultÃ¡neamente 
* Permitir la escritura  de 1 registro, acorde a la seÃ±al de control regwrite
* Contar con seÃ±al de rst, la cual  ponga  todos los registros en un valor conocido.

![cn](https://github.com/Fabeltranm/SPARTAN6-ATMEGA-MAX5864/blob/master/lab/lab07-BancosRgistro/doc/caja%20negra.png)

* Visualizar la informaciÃ³n, en al menos dos display de 7 segmentos (informaciÃ³n de cada registro leÃ­do).
* El ingreso de la informaciÃ³n se debe hacer por medio de los interruptores.


**Opcional. Da mas puntos:**
* Parametrizar el tamaÃ±o de palabra de cada registro  y la cantidad de registro ( Por defecto =4 bits). Se recomienda leer el documento de este [link](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-884-complex-digital-systems-spring-2005/related-resources/parameter_models.pdf) .
* Pre cargar el banco de registro con informaciÃ³n.  _Usar $readmenh_  (Investigar: "Initialize Memory in Verilog").

Entregables:

* DocumentaciÃ³n
* Archivo `testbench` el cuÃ¡l debe simular la escritura de 16 registros y 8 lecturas mas el rst, el resultado de la simulaciÃ³n debe visualizarse en diagrama de tiempo.
* VÃ­deo de la implementaciÃ³n.
* CÃ³digo HDL de la soluciÃ³n.
.

 ![caja](https://github.com/Fabeltranm/SPARTAN6-ATMEGA-MAX5864/blob/master/lab/lab07-BancosRgistro/doc/banco%20registro.png)


## EspecificacÃ³n

Banco de registro tenemos una memoria que cuenta con 16 espacios de memoria en el cual podemos escribir mediante selectores o interruptores. 
Con estos interruptores podemos generar un número binario para almacenar en algun registro de memoria.
Contamos con un interruptor llamado reset (RST) de 1 bit que es el encargado de poner nuestros espacios de memoria en 0 cuando este sea necesario. Tenemos una señal de reloj (CLK) de 1 bit que se activa solo en flanco de subida dando cada flanco de subida un 1 y un 0 para su flanco de bajada. Registro Write (regWrite): el registro es una entrada a nuestro banco de registro de 1 bits se puede manejar mediante un interruptor de escritura (1) o lectura (0) con este interruptor podemos escoger si queremos leer o escribir algún dato. Dirección de registro (addrW): es una entrada a nuestro banco de registro de 2 bits, tiene la función de escoger el banco en el que se quiere guardar el dato de memoria en un registro.

Registro de escritura (datW): es una entrada de 4 bits que se encarga de darnos el VALOR del dato que vamos a guardar en nuestro registro. 
Tenemos también 2 salidas (datOutRa), (datOutRb) de 4 bits cada salida, con la función de indicarnos el resultado final. 
Adicionalmente, mostraremos unos tópicos sobre la composición de del sistema de memoria, las instrucciones de registro están en la jerarquía de la arquitectura de un microprocesador, los registros son claves, para la construcción de circuitos de bloques secuenciales. 

Los registros, aunque se ejecutan de manera concurrente, se debe sincronizar las señales con el reloj. 
Como muestra la figura es la forma fundamental y básica, de cómo se muestran las secuencias de estado de los bancos de registro

![secuencia](https://github.com/ELINGAP-7545/lab06-lab05-grupo-11/blob/master/secuencias%20de%20estado.PNG)

##Diagrama de flujo propuesto pra el banco de registro. 

## Desarrollo de la practica

#### DescripciÃ³n
Por medio de los conceptos recibidos en el contenido de la tematica tratada durante las sesiones de clase se procede a realizar un desarrollo con bancos de registros, en donde se tiene el control de los saltos mediante registros de entrada de 2bits y 4 bits como son:
####	reg [1:0] addrRa; lectura
####    reg [1:0] addrRb; lectura
####	reg [3:0] addrW;  Escritura
####	reg [3:0] datW;   Escritura

#### addrRa y addrRb son los registros que permiten seleccionar la posiciÃ³n del banco de registros que se desea visualizar en las salidas denominadas datOutRa y datOutRb  , en este caso las posiciones de registros se observan de la siguiente manera:

## Entradas 
#### breg[0] <= 9;  //  1001 
#### breg[1] <= 7;  //  0111
#### breg[2] <= 5;  //  0101
#### breg[3] <= 1;  //  0001
		
## Salidas
#### datOutRa
#### datOutRb

#### En las diferentes posiciones de entrada del banco de registros se encuentran cargados por defecto valores como son 9"1001", 7 "0111",5 "0101",1 "0001". asi.
