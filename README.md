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

El funcionamiento escencial del circuito se resume en el siguiente diagrama de bloques.

![]()

**Figura 14. Diagrama de bloques del funcionamiento de la calculadora**

**6. LISTA DE COMPONENTES**

Toda la simulación e implementación se lo realizó en Thinkercad. Sin embargo, para llegar a un diseño ideal, se necesitó las siguientes herramientas.
- Constructor Virtual de Circuitos
- Multisim
- Proteus

Y dentro de ello, se implemento los siguientes componentes:
- 8 Regletas básicas de Protoboard
- Fuente de alimentación
- Cables
- 3 Conjuntos de 8 interruptores
- 2 Conjuntos de 8 LEDs
- Conjunto de 4 displays de siete segmentos
- 6 Sumadores 74LS83
- 2 Decodificadores BCD a siete segmentos 74LS57
- 4 Puertas básicas NOT 74LS04
- 2 Puertas básicas XOR 74LS86
- 2 Puertas básicas AND 74LS08
- 1 Puerta básica OR 74LS32

**7. MAPA DE VARIABLES**

Las variables están constituidas como:

Variables de entrada:
- Número A de 8 bits
- Número B de 8 bits
- Nivel de selección

Variables Locales:

Se sigue de acuerdo a cada proceso
1. Sumador
- Entradas: números A y B de 8 bits
- Intermedio: acarreo inicial = 0.
- Salidas: resultado de la suma y acarreo.

2. Restador
- Entradas: números A y B de 8 bits
- Intermedio: acarreo inicial = 1.
- Salidas: resultado de la resta y signo.

3. Multiplexación
- Entradas: bit del resultado de la suma, bit del resultado de la resta, siendo que ambos tengan el mismo valor posicional; y bit de selección
- Salidas: bit seleccionado.

4. Decodificación
- Entradas: número binario multiplexado
- Salidas: representación el LEDs

Variables de Salida:
- Número Resultado de 8 bits (o 9 si existiera acarreo).
- Signo del resultado

**8. EXPLICACIÓN DEL CÓDIGO FUENTE**

En nuestra conveniencia, el procedimiento iniclamente se dividió en dos partes en la cuál sus salidas serán seleccionadas y ese resultado será mostrado. detallamos cada uno de los siguientes procesos:

**8.1. Sumador**

Para la implementación del circuito integrado 74LS283, este solo nos permite el ingreso de un número binario de cuatro bits. Entonces, como en la suma ordinaria siempre se comienza sumando desde las cifras menos significativas hasta las cifras más significativas, entonces la primera suma consistirá en operar con los cuatro bits menos significativos sin acarreo inicial debido a que no menciona tal condición. Este resultado producirá un número en la cuál debe ser los cuatro bits menos significativos del resultado. Sin embargo, esta suma puede que produzca un acarreo y no sería lógico que ese acarreo sea como un bits más por lo que ese acarreo de salida del primer smador vendrá a ser el acarreo de entrada del segundo sumador. Así que para el segundo sumador, las entradas serán los 4 siguientes bits más significativos de ambos números con el acarreo y resultado de ello producirá un número binario, donde sus cuatro bits serán los más significativos. El acarreo de salida que produciría representa el bit más 2. 

![]()

**Figura 15. Esquema eléctrico del sumador**

**8.2. Restador**

Sigue la misma lógica del circuito sumador, es decir, operar dígito por dígito de drecha a izquierda. En este caso, el segundo número deberá estár complementado para producir esa diferencia, pero hay que tomar en cuenta que el resultado de la resta produciría números positivos como negativos debido a que se resta un número mayor con un número menor o un número menor con un número mayor. La forma más utilizada de realizar la resta es utilizando el complemento a 2. Este consiste en trasnformar al número sustraendo a complemento a 1, es decir, cambiar los 0s por 1s y los 1s por 0s, y a partir de ello sumar 1 a ese resultado. Entonces, en la resta de los bits menos significativos, las entradas del segundo número irán con inversores ya que representa la complementación de ese número y el acarreo inicial irá con nivel alto ya que se esta sumando a 1 considerando la condición del complemento a 2. Los acarreos intermedios se conectarán de la misma forma de la suma. 

![]()

**Figura 16. Esquema eléctrico del la primera parte del restador**

El resultado por medio de ambos sumadores es el resultado final si se resta un número menor con un número mayor, pero no será lo mismo si llegara a ser un número negativo. Algo interesante es que cuando se resta un número mayor con un número menor, el resultado del acarreo es 1, mientras que si se realiza por el contrario, el acarreo es 0. En pocas palabras, si el acarreo es 1 el número resultado se mantendrá, sino, el número debera transformarse a complemento a 2. Para ambos casos, se aplica el siguiente procedimiento:
1. Se invierte el acarreo
2. Cada bit de número resultado llega a ser una entrada de la compuerta XOR.
3. La segunda entrada de todas las compuertas es el bit de acarreo invertido.
4. Las salidas de las compuertas XOR irán conectadas a cada entrada de otros dos sumadores desde los menos significativos.
5. El acarreo inicial del sumador menos significativo es el bit del signo invertido.
6. El resultado de la suma es el resultado válido tanto para un número positivos como un número negativo.
7. El signo de la resta representa el acarreo de salida invertido de la operación de los dos primeros sumadores.

![]()

**Figura 17. Esquema eléctrico todo el restador**

**8.3 Multiplexación**

La forma más sencilla de multiplexar las salidas es utilizando un multiplexor tipo 2 a 1 debido a que se están realizando dos operaciones y se quiere visualizar una. Entonces, se requiere de 8 multiplexores, uno por cada dígito en la cuál el selector de datos común tendrá dos estados: 0 para la suma y 1 para la resta. El resultado de esa multiplexación son los dígitos de cada operación.

![]()

**Figura 17. Esquema eléctrico de la multiplexación de salidas**

**8.4. Decodificación**
Se representará en LEDs los digitos manejando el nivel de lógica positiva.

**8.5. Resultados**
Los resultados se muestran tanto la simulación en proteus, en Tinkercad como en el constructor virtual de circuitos.

![]()

**Figura 18. Implementación realizada en Proteus**

![]()

**Figura 19. Implemetación realizada en Tinkercad**

![]()

**Figura 20. Implementación realizada en el Constructor Virtual de Circuitos**

**9. DESCRIPCIÓN DE PRERREQUISITOS Y CONFIGURACIÓN**

Como se lo realizó de forma virtual, solo se requieriría de una computadora con conexión a internet. Es recomendable tener una memoria RAM de 3GB para adelante para el adecuada simulación en el Tinkercad.

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

**13. BIBLIOGRAFÍA**
- Tocci, R., Widmer, N. and Moss, G., 2007. Sistemas Digitales. 10th ed. México: Pearson Educación, pp.317 - 331.
- Anirudh Kumar Maurya, K., Rama Lakshmanna, Y., Bala Sindhuri, K., & Udaya Kumar, N. (2017). Design and implementation of 32-bit adders using various full adders. 2017 Innovations in Power and Advanced Computing Technologies, i-PACT 2017, 2017–January, 1–6. https://doi.org/10.1109/IPACT.2017.8245176
- Chowdhury, A. K., Tan, D. Y. W., Yew, S. L. B., Wyai, G. L. C., Madon, B., & Thangarajah, A. (2015). Design of full adder/subtractor using irreversible IG-A gate. I4CT 2015 - 2015 2nd International Conference on Computer, Communications, and Control Technology, Art Proceeding, 103–107. https://doi.org/10.1109/I4CT.2015.7219546
- Cosío, P. (n.d.). (No Title).
- Electrónica Digital UCN: Restador. (n.d.). Retrieved July 31, 2020, from http://electroucn.blogspot.com/2014/06/Restador.html
- Kumar, P. K., Rao, P. P., & Kakarla, H. K. (2017). Optimal design of reversible parity preserving new Full adder / Full subtractor. Proceedings of 2017 11th International - - Conference on Intelligent Systems and Control, ISCO 2017, 368–373. https://doi.org/10.1109/ISCO.2017.7856019
- Restador completo – Cursos gratis. (n.d.). Retrieved July 31, 2020, from https://www.conocimientosweb.net/dcmt/ficha7419.html
