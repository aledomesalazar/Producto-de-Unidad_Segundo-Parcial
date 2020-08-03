# Producto de Unidad - Segundo Parcial
## Diseño de una calculadora binaria de 8 bits

**1. PLANTEAMIENTO DEL PROBLEMA**

Las operaciones algebraicas entre números binarios son muy importantes en cualquier sistema digital. Realizar estas operaciones con números binarios pequeños de forma manual es bastante sencillo, pero realizar operaciones con números cada vez de mayor tamaño de esta forma se vuelve más complicado. Por medio del algebra booleana, se puede representar las expresiones lógicas en la cuál describirá la conexión de compuertas fundamentales como la AND, OR y NOT. Además, el circuito dígital implementado se puede reducir por medio de sus leyes y también por los mapas de Karnaugh. Ventajosamente, se desarrollaron circuitos integrados que permiten realizar estas operaciones de forma directa y esos resultados se los puede representar en una mejor forma visual por medio de dígitos numéricos decimales a través de decodificadores. El desafío es realizar una calculadora que sume y reste números con esos CI, en base a los conocimientos adquiridos hasta la fecha.

**2. OBJETIVOS**

**2.1. Objetivo General**

Realizar el diseño y la implementación en Tinkercad de una calculadora pequeña que realice la suma y la resta entre dos números binarios de 8 bits cada uno.

**2.2. Objetivos Específicos**
- Diseñar un circuito sumador y un circuito restador.
- Aprender el uso de los multiplexores y su aplicación en la selección de salidas.
- Representar los resultados de las operaciones en display de siete segmentos a partir de decodificadores teniendo entradas de núneros binarios.

**3. ESTADO DEL ARTE**

*Design and Implementation of 32-Bit Adder Using Various Full Adders* 

 Los ingenieros K. Anirudh Kumar Maurya, K.Bala Sindhur, Y.Rama Lakshmanna y N.Udaya Kumar de la Universidad de Ingenieria SRKR en Bhimavaram, India publicaron un artículo en el año 2017, donde exponían el diseño e implementación de varios sumadores de 32 bits como el Ripple Carry Adder o el Carry Increment Adder. Los resultados de estos diseños fueron obtenidos mediante la utilización de un código de programación de Verilog en Xilinx versión 14.5. 
(Anirudh Kumar Maurya, Rama Lakshmanna, Bala Sindhuri, & Udaya Kumar, 2017)

*Optimal Design of Reversible Parity Preserving New Full Adder/ Full Subtractor*

El profesor P.Prasad Rao, el profesor asociado Kakarla Hari Kishore y el becario de investigación P.Kiran Kumar publicaron en el año 2017 un artículo que tiene como propósito el diseño de un sumador y un restador completo utilizando la lógica reversible. Esto con la finalidad de desarrollar un circuito que sea tolerante a las fallas y que consuma la menor energía posible. El circuito posee varias características como son una menor complejidad en su diseño, menor utilización de compuertas y que la paridad de entrada sea la misma que la de salida haciendo que este circuito sea llamado circuito de preservación de paridad.
(Kumar, Rao, & Kakarla, 2017)

*Design of Full Adder/Subtractor using Irreversible IG-A Gate*

Los investigadores Adib Kabir Chowdhury, Daniel Yong Wen Tan, Simon Lau Boung Yew, Gary Loh Chee Wyai y Bakri Madon de la Universidad Tecnológica Sarawak en Sibu, Malaysia y el investigador Akilan Thangarajah de la Universidad de Windsor en Ontario, Canadá publicaron en el año 2015 un artículo que propone un diseño de una puerta IG-A irreversible. Esta compuerta es utilizada para la construcción de sumadores y restadores, además este diseño es comparable con los diseños de las compuertas que utilizan la lógica reversible. 
(Chowdhury et al., 2015)

**4. MARCO TEÓRICO**

**4.1. Circuitos sumadores**

*4.1.1. Circuito Sumador*

Los circuitos sumadores son circuitos muy utilizados en distintos tipos de sistemas digitales. Para comprender efectivamente el funcionamiento de un circuito sumador, primero se debe entender el funcionamiento de un semisumador. El semisumador realiza únicamente la suma de dos números binarios con un bit cada uno. 

![]()

**Figura 1. Diagrama de bloque de un circuito semisumador**

![]()

**Figura 2. Tabla de verdad de circuito semisumador**

![]()

**Figura 3. Esquema eléctrico del circuito semisumador**

El circuito presentado anteriormente no es considerado de mucha utilidad, ya que siempre se suma más de un bit. Para la suma en binario siempre se utiliza un bit de acarreo, que es el resultado de la suma de las operaciones anteriores. Es por esta razón que se necesita de un circuito que incluya como parte de sus entradas el bit de acarreo de las suma anterior. A este circuito se lo denomina como sumador completo.

![]()

**Figura 4. Diagrama de bloque de un circuito sumador completo**

![]()

**Figura 5. Tabla de verdad de circuito sumador completo**

![]()

**Figura 6. Esquema eléctrico del circuito sumador completo**

*4.1.2. Circuito restador*

Un semirestador es un circuito combinacional que resta dos bits y produce su respectiva diferencia. Posee dos entradas que son el minuendo (x) y el sustraendo (y). Para realizar la diferencia se debe verificar las magnitudes relativas del minuendo y del sustraendo, cuando el minuendo es menor que el sustraendo es necesario pedir prestado un 1 lógico de la siguiente etapa más alta. En la salida se generan dos bits de salida el de la diferencia (D) y el bit del préstamo (B). El semirestador cuenta con la siguiente tabla de verdad.

![]()

**Figura 7. Esquema eléctrico del circuito resrador**

De la tabla de verdad se obtiene que la diferencia puede ser representada por medio de una compuerta XOR y el préstamo puede ser representado por la expresión X’Y.  Dando el siguiente esquema como resultado.

Un restador completo es un circuito combinacional que realiza la resta entre dos bits tomando en consideración que un 1 lógico ha sido tomado prestado por la etapa significativa más baja. El circuito posee tres entradas que son el minuendo (x), el sustraendo (y) y el préstamo de entrada (z) y posee dos salidas que son la diferencia (D) y el préstamo de salida (B). Un restador completo posee la siguiente tabla de verdad.

![]()

**Figura 8. Diagrama de bloque de un circuito restador completo**

![]()

**Figura 9. Tabla de verdad de circuito restador completo**

![]()

**Figura 10. Esquema eléctrico del circuito restador completo**

*4.1.3. Circuito Sumador - Restador*

El circuito sumador en paralelo básico puede usarse para sumar o restar, dependiendo de si el número B se deja sin cambio o se convierte en su complemento a 2.
Este circuito sumador/restador se controla mediante las dos señales de control
SUMA y RESTA.

- Cuando el nivel de SUMA es ALTO y RESTA es BAJO: 
1. Acarreo de C0 = 0
2. Habilita las compuertas AND 1, 3, 5 y 7 
3. Deshabilita las compuertas AND 2, 4, 6 y 8
4. Pasan los niveles B0, B1, B2 y B3 en forma respectiva.
5. Los niveles B0 a B3 pasan a través de las compuertas OR en el sumador en paralelo de cuatro bits, para que se sumen a los bits A0  A3.
6. La suma aparece en las salidas S0 a S3.

- Cuando el nivel RESTA es ALTO y SUMA es BAJO:
1. Acarreo de C0 = 1.
2. Habilita las compuertas AND 2, 4, 6 y 8. 
3. Deshabilita las compuertas AND 1, 3, 5 y 7.
4. Pasan los niveles B0’, B1’, B2’ y B3’ en forma respectiva.
5. Los niveles B0’ a B3’ pasan a través de las compuertas OR en el sumador en paralelo de cuatro bits, para que se sumen a los bits A0  A3.
6. La diferencia aparece en las salidas S0 a S3.

![]()

**Figura 11. Circuito sumador - restador**

Un circuito multiplexor es un circuito digital que selecciona una de las múltiples entradas que posee y su valor lógico es enviada por la única salida que posee el circuito. Esta selección de datos es realizada mediante una o varias entradas de selección. La codificación binaria que resulta de las entradas S indica el índice de la entrada I que es conducida a la salida. 
El siguiente esquema es la representación de un circuito multiplexor de dos entradas.

![]()

**Figura 12. Esquema básico del funcionamiento de un multiplexor de 2 entradas.**

De la tabla de verdad se obtiene que cuando la entrada de selección (S) es igual a cero la salida es igual a la entrada I0, en cambio, cuando la entrada de selección es igual a uno entonces la salida es igual a la entrada I1. Lo que puede hacer que la siguiente tabla de verdad reemplace a la anterior tabla de verdad.

![]()

**Figura 13. Tabla de verdad de un selector de 2 a 1**

De la tabla de verdad se obtiene que cuando la entrada de selección (S) es igual a cero la salida es igual a la entrada I0, en cambio, cuando la entrada de selección es igual a uno entonces la salida es igual a la entrada I1. 

**5. DIAGRAMAS**

**6. LISTA DE COMPONENTES**

**7. MAPA DE VARIABLES**

**8. EXPLICACIÓN DEL CÓDIGO FUENTE**

**9. DESCRIPCIÓN DE PRERREQUISITOS Y CONFIGURACIÓN**

**10. CONCLUSIONES**
1. El diseño de una calculadora capaz de realizar la suma y la resta entre dos números binarios de ocho bits cada uno, terminó siendo un diseño bastante complejo. Desde considerar la complementación del segundo números para realizar la resta hasta realizar la multiplexión del resultado para, posteriormente, ser mostrado en los display de siete segmentos; el proyecto terminó por evaluar todos los conocimientos adquiridos en clases para ser llevado a cabo con éxito.
2. El diseño del circuito sumador fue un diseño consideradamente más sencillo en contraposición al diseño del circuito restador. Para realizar el circuito sumador de ocho bits solo se necesitaba realizar una conexión en cascada entre los integrados 74LS83. En cambio, para realizar el circuito restador se necesitaba considerar la complementación del segundo número binario para realizar la suma. 
3. Los circuitos multiplexores son circuitos que permiten seleccionar una entrada entre varias y enviar su valor a única salida. Su funcionamiento fue de gran importancia en el diseño de la calculadora pequeña ya que permitió mostrar el resultado de la suma o el resultado de la resta en función de lo que el usuario necesite.
4. La utilización de displays de siete segmentos para mostrar el resultado de las operaciones, resultó un proceso bastante largo de implementar. El resultado de las operaciones era dado en el sistema binario, el cual se debió transformar a código BCD para poder utilizar los integrados 4511 que convertían el valor BCD a siete segmentos. 

**11. RECOMENDACIONES**
1. Para realizar el diseño de una calculadora simple, se recomienda realizar distintos diagramas del diseño que puedan ser comprobados antes de llevar a cabo la implementación del dispositivo.
2. Se recomienda comprender claramente los complementos A1 y A2, esto con la finalidad de incorporarlos correctamente en el diseño de un circuito restador.
3. Con la finalidad de evitar errores y garantizar un buen manejo de los circuitos multiplexores en el diseño de una calculadora pequeña, se recomienda investigar detalladamente sobre su construcción y su correcto funcionamiento.
4. Se recomienda investigar distintos métodos de conversión entre los sistemas binario al sistema BCD esto con la finalidad de ahorrar recursos en el momento de la implementación de la calculadora pequeña.

**12. CRONOGRAMA**
