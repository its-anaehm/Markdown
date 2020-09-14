# **Ensayo #1**

    IS-513 Lenguajes de Programación
    Ana Evelin Hernández Martínez
    aehernandezm@unah.hn
    20171001620

## **1. ÍNDICE**

- [**Ensayo #1**](#ensayo-1)
  - [**1. ÍNDICE**](#1-índice)
  - [**2. Introducción: LENGUAJES DE PROGRAMACIÓN 101**](#2-introducción-lenguajes-de-programación-101)
  - [**3. Historia Y Evolución De Los Lenguajes De Programación**](#3-historia-y-evolución-de-los-lenguajes-de-programación)
    - [**3.1 Lenguajes de Programación**](#31-lenguajes-de-programación)
    - [**3.2 Historia de los Lenguajes de Programación**](#32-historia-de-los-lenguajes-de-programación)
      - [**3.2.1 Línea de Tiempo desde el comienzo de los primeros lenguajes tenemos**](#321-línea-de-tiempo-desde-el-comienzo-de-los-primeros-lenguajes-tenemos)
  - [**4. Análisis Léxico**](#4-análisis-léxico)
  - [**4.1 Tokens**](#41-tokens)
  - [**5. Análisis Sintáctico**](#5-análisis-sintáctico)
  - [**5.1 Parseo**](#51-parseo)
    - [**5.2 Gramáticas Libres de Contexto  -  CFG**](#52-gramáticas-libres-de-contexto---cfg)
    - [**5.3 Árboles de Derivación**](#53-árboles-de-derivación)
  - [**6. Análisis Semántico**](#6-análisis-semántico)
  - [**7. Fases de Compilación**](#7-fases-de-compilación)
  - [**8. Diagramas de Estado**](#8-diagramas-de-estado)
  - [**9. Autómatas Finitos**](#9-autómatas-finitos)
  - [**10. Referencias**](#10-referencias)

## **2. Introducción: LENGUAJES DE PROGRAMACIÓN 101**

En algunas universidades de los EE.UU se acostumbra el hecho de que en sus clases más basicas las identifiquen con el código 101 por poner un ejemplo "Math 101" sería una clase que incluye dentro de su temática todos los conceptos básicos del algebra (suma, resta, multiplicación y división). Para este caso nos referimos a los **Lenguajes de Programación 101** con el objetivo de identificar y generalizar muchos conceptos claves y basicos que nos lleven a un pleno entendimiento del tema.

## **3. Historia Y Evolución De Los Lenguajes De Programación**

---

### **3.1 Lenguajes de Programación**

Los lenguajes de Programación son un conjunto de símbolos y palabras, instrucciones y sentencias que un usuario tiene a su posición para elaborar un programa. Es básicamente la forma en que el usuario se puede comunicar con el computador.

Los podemos clasificar de la siguiente manera:

- **Lenguajes de Bajo Nivel:** Son los que se acercan al funcionamiento de la computadora.
  - *Lenguaje Máquina:* Es el programa de programación que entiende la computadora, utiliza el alfabeto binario es decir el 0 y el 1 creando cadenas binarias con las que se elaboran instrucciones que la CPU del ordenador procesa.
  - *Lenguaje Ensamblador:* Con la aparición de este lenguaje se crearon los programas traductores para pasar los programas escritos en lenguaje ensamblador a máquina neumónicos.

- **Lenguajes de Medio Nivel:** Tienen características que los acercan a los lenguajes de bajo nivel pero al mismo tiempo ciertas cualidades que lo hacen un lenguaje más cercano al humano aún así tiene muchos inconvenientes puesto que se necesitan de muchas instrucciones para realizar tareas muy simples.

- **Lenguajes de Alto Nivel:** Estos lenguajes están diseñados para que los programadores escriban y entiendan instrucciones lo más parecido al lenguaje humano lo que hace que se requieran menos tiempo a la hora de realizar un programa, son los más utilizados hoy en día.
  
### **3.2 Historia de los Lenguajes de Programación**

---

Podemos remontar los orígenes de la programación hacía unos siglos atrás ya que no se contaba con un instrumento que les ayuda a archivar y a procesar la información. Luego viene la necesidad de crear el dinero y con eso el manejar cuentas exactas entonces por eso se crea el ábaco. Gracias a instrumentos como este es que la humanidad pudo comenzar a contar y dar lo que serían los primeros pasos para emprender el camino de los lenguajes de programación. Muchos tiempo después se crean máquinas como la pascalina para crear registros contables, la máquina de telar en la que se podían reproducir patrones en los tejidos leyendo la información codificada en tablones de papel rígido; así es como al principio en la creación de computadores se guardaba la información. Luego Babbage crea la máquina analítica que era capaz de hacer todas la operaciones matemáticas y ser programada a través de tarjetas de cartón perforado y era capaz de almacenar mucha información; por esto es que se le conoce a Babbage como el padre de la computación.

Posteriormente a todos estos inventos vinieron otros como la máquina tabuladora, entre otros, hasta llegar a 1920 cuando Arthur Schrblus creó ENIGMA una máquina alemana que permitía usarse para cifrar y descifrar mensajes. En 1936 Alan Turing crea la Máquina de Turing la cual consistia en un mecanismo retórico que manipula símbolos en una cinta que puede ser adaptada para simular la lógica de cualquier algoritmo de computación (Gracias a esto Turing es considerado el padre de la informática moderna).

Entre 1936 y 1938 Conrad Zuse fabricó y diseñó la Z1, era una calculadora mecánica binaria operada con electricidad. Los datos los recibía de cintas perforadas y aunque no entendía un lenguaje de programación tal y como lo entendemos hoy la Z1 sería para muchos la primera computadora programable de la historia.

En 1943 y el proyecto Electronic Numerical Integrator and Computer (ENIAC) fue creado por John Williams y John Prester con el propósito de resolver los problemas de balística del ejército de los EE.UU. En 1945 John Von Newman desarrolló una técnica que establecía las instrucciones complejas que se deben utilizar para comprobar el hardware simple permitiendo que se pudiese programar rápidamente.

En 1950 la programación en lenguaje máquina resulta ser muy lenta y tediosa puesto que los datos se deben de introducir en sistema binario y además obliga a conocer las posiciones de memoria dónde se almacenan los datos (por lo que este tipo de programación como podemos imaginar conlleva un gran número de errores y la tarea de depuración exige bastante tiempo y dedicación). A principios de los años 50 se crea una notación denominada código de ensamblaje en este se utiliza una serie de abreviatura y técnicas para representar las operaciones. En 1951 Grace Murray Hopper inventa el primer compilador el cual permite generar un programa binario a partir de un código fuente.

---

#### **3.2.1 Línea de Tiempo desde el comienzo de los primeros lenguajes tenemos**

---

- En 1953 John Backus creó el primer lenguaje de alto nivel *SPEEDCODING* para el IBM 701 y que este pudiese soportar la computación con números de coma flotante.

- En 1957 IBM desarrolla **Fortran** el cual sería el primer lenguaje de programación universal, desarrollado específicamente en bakú solo crea para crear computaciones científicas matemáticas y estadísticas de alto nivel, es el lenguaje más antiguo en uso.

- En 1958 se crea **ALGOL 58** (Algoritmic Language) el primer lenguaje algorítmico que durante los años 60 fue muy popular aunque no fue utilizado comercialmente.
  
- También en 1958 John MaCarthy crea **LISP** como parte de un proyecto de inteligencia artificial, el cual sería la base de la programación orientada a objetos.

- Entre 1959 y 1960 se crea **COBOL** (Common Business Oriented Language) que sería el segundo lenguaje de programación universal, fue creado mediante la supervisión de Grace Murray Hopper y su funcionalidad es utilizada exclusivamente en algunos grandes sistemas informáticos de entidades bancarias.
  
- En 1962 Ole-Johan y Kristen Nygaard crean **Simula** un lenguaje de programación orientado a objetos, posteriormente serían la base de la creación de otros lenguajes por su orientación a objetos, así fue como se popularizaron términos como clases, objetos, instancias, etc.
  
- En 1964 John G. Kemeny y Thomas E. Kurtz crean **BASIC** (Beginners All-Purpose Symbolic Instruction Code) fue desarrollado como un lenguaje simplificado para aquellos que no tenían como bases fuertes conocimientos técnicos o matemáticos.
  
- 1969 y Kenneth Thompson y Dennis Ritchie crean **B** lenguaje de programación pensado para UNIX que sería predecesor de lenguajes como C.

- 1970 y Niklaus Wirth crea **PASCAL** el cual en sus inicios se crea como una herramienta de enseñanza y este se popularizó por su uso comercial. PASCAL se caracteriza por ser un lenguaje de programación estructurado fuertemente tipificado (esto implica que el código está dividido en porciones fácilmente legibles llamadas funciones o procedimientos y los datos de las variables deben ser declarados previamente a su uso).
  
- 1972 y es cuando Dennis Ritchie crea **C** un lenguaje orientado a la implementación de sistemas operativos concretamente UNIX; C es apreciado por la eficiencia del código que produce y es el más popular para crear software de sistema.
  
- También en 1972 llega **PROLOG** (Programation Logique) creado por un grupo dedicado al estudio de la inteligencia artificial de la universidad Aix-Marseille, es un lenguaje declarativo por excelencia (los lenguajes creados antes que PROLOG eran algorítmicos) es decir que no está basado en órdenes sino en descripciones, es decir se le da al ordenador una serie de conocimientos sobre un tema junto con una serie de reglas y el programa nos contestara a todas las preguntas que deseemos hacerle sobre el tema siempre que las respuestas pueda deducirse lógicamente.
  
- En 1980 llega **ADA** nombrado de esta forma en honor a Ada Lovelace (Primera programadora de la Historia) es derivado de PASCAL; este es un lenguaje de programación orientado a objetos y fuertemente tipificado, fue diseñado por James Ichbiah por encargo del departamento de defensa de EE.UU.
  
- En 1983 y Bharne Stroustrup modificó el lenguaje C a **C++** al que muchos consideran como el lenguaje de programación más popular que ha existido; la POO se considera como la mejor y la más fácil de programar.
  
- En 1983 también Brad Cox y Thom Love crearon **Objective-C** que es una ampliación de C.
  
- 1987 Larry Wall crea **PERL** tras extraer datos de un informe y darse cuenta que UNIX no podía llevar a cabo las operaciones que él necesitaba fue descrito por el mismo Larry como un lenguaje consigue que haga su trabajo y posee características de C y es de los más usados en los servidores web.
  
- En 1991 Guide Van Rossum crea **Python** que es un lenguaje de programación interpretado e interactivo capaz de ejecutarse en una gran cantidad de plataformas, sus principales usos son en aplicaciones web, desarrollo de software y seguridad informática.
  
- En ese mismo año se crea **VisualBasic** por Alan Cooper que es un lenguaje de programación dirigido por eventos (este lenguaje es un dialecto de Basic con importantes agregados).

- 1993 y Yukihiro Matsumoto crea **Ruby** fusionando aspectos de sus lenguajes favoritos entre ellos PERL, Ada, LISP, etc. Es un lenguaje de programación dinámico y de código abierto enfocado en la simplicidad y productividad.
  
- En 1995 se crean 3 lenguajes muy importantes para la historia de la programación:
  - ***PHP:*** Creado por Rasmus Lerdorf que es un lenguaje que ha crecido exponencialmente hasta llegar a ser parte de una arquitectura web integrada.
  - ***Java:*** Creado por un equipo de desarrolladores de Sun Microsystems dirigido por James Gosling, es actualmente uno de los lenguajes de programación más utilizado en el mundo, sus principales usos son en programación web, desarrollo de aplicaciones web, desarrollo de software, etc.
  - ***JavaScript:*** Fue originalmente desarrollado por Brendan Eich, diseñado con influencia del lenguaje C, es un lenguaje de alto nivel creado para extender las funcionalidades de las páginas web, sus principales usos son en el desarrollo de web dinámica, navegadores web, widgets, etc.

![Línea de Tiempo Historica de los Hechos más relevantes en la Historia de los Lenguajes de Programación](https://drive.google.com/uc?export=view&id=1wiR8wBDWEq27TLD3CUpBIYizm9SW5Cm1 "Línea de Tiempo.")

## **4. Análisis Léxico**

## **4.1 Tokens**

---

Un token es un componente léxico, una cadena de caracteres que tiene un significado coherente en ciertos lenguajes. Los tokens podrían ser por ejemplo los condicionales ***if y else***, ***for o while** que se utilizan para bucles; también podrían ser variables o los tipos de variables, números, signos, un operador de varios caracteres, etc. que sirven como identificadores. Los tokens son elementos básicos que son desarrollados para una traducción de algún tipo de programa.

## **5. Análisis Sintáctico**

## **5.1 Parseo**

---

El Parseo o la realización de un análisis sintáctico toma como entrada un flujo de tokens provenientes del analizador léxico y retorna como resultado un árbol de derivación (árbol de parseo) que crea de manera implícita o explícita; las hojas de este árbol son tokens provenientes del flujo de tokens. Otro insumo esencial para el analizador sintáctico es la gramática libre de contexto.

### **5.2 Gramáticas Libres de Contexto  -  CFG**

Definiendo las gramáticas de un lenguaje formal como una serie de reglas de derivación, producción o reescritura conformadas por los siguientes elementos:

- *Símbolos no Terminales:* que representan aquellos elementos dentro de un programa que se componen de otras partes más pequeñas.
- *Símbolos Terminales:* Corresponden a los elementos de un programa que no tiene sentido dividirlos en partes más pequeñas ya que pierden su significado.
- *Producciones:* Una producción es la relación entre un símbolo no terminal y una secuencia de símbolos terminales o no terminales de los cuales se componen.
- *Símbolo inicial:* Está determinado por un único no terminal.

Las CFG tienen reglas de producción de la forma:

    A → 𝛾 

Donde 𝛾 es una combinación de terminales y no terminales. Donde a partir de algún no terminal a la izquierda podemos generar cualquier combinación de terminales y no terminales a la derecha. Estas gramáticas se comportan como cualquier otra con la diferencia de que el símbolo inicial sólo puede ser uno no terminal y que la derivación sólo puede partir de un único no terminal para derivar en una cadena conformada por terminales y/o no terminales.

### **5.3 Árboles de Derivación**

Los árboles de derivación se utilizan como una manera de representar una estructura sintáctica de las cadenas en una gramática libre de contexto y son utilizados en uno de los pasos fundamentales de la compilación de muchos lenguajes de programación. Se comporta como un grafo conexo con un único nodo raíz en la parte superior y sin ciclos de tal forma que desde la raíz sólo existe un único camino para llegar a todos los demás nodo.

Un árbol de análisis de parseo correspondiente a una derivación es un árbol etiquetado:

- Los nodos interiores están etiquetados por no terminales.
- Los nodos hoja están etiquetados por terminales.
- Los nodos hijos de cada nodo interno representan el remplazo del no terminal asociado en un paso de la derivación
  
**Ambigüedad en los árboles de parseo:**

- Se dice que una gramática que produce más de un árbol de derivación para alguna frase es ambigua.
- Para algunos tipos de analizadores es preferible que la gramática no sea ambigua ya que necesitan un árbol exclusivo por frase.
- Algunos analizadores proporcionan métodos para admitir gramáticas ambiguas pero con especificaciones adicionales que permiten la generación de un único árbol por frase.

![Árboles de Derivación](https://drive.google.com/uc?export=view&id=1BxSKrumsvNvZBRV4fYStqYPJ75-xpbr- "Árboles de derivación.")

## **6. Análisis Semántico**

El analizador semántico usa la información en el árbol de sintaxis y la tabla de símbolos para verificar la consistencia semántica entre el programa fuente y la definición del lenguaje. También recopila información de tipo y la guarda en un árbol de sintaxis o tabla de símbolos para su uso posterior durante la generación de código intermedio.

Una parte importante del análisis semántico es la verificación de tipo, donde el compilador verificará si cada operador tiene un operando coincidente. Por ejemplo, muchas definiciones de lenguaje de programación requieren que los índices de matriz sean enteros. Si la matriz se indexa con números de coma flotante, el compilador debe informar un error.

Una parte importante del análisis semántico es la verificación de tipo, donde el compilador verificará si cada operador tiene un operando coincidente. Por ejemplo, muchas definiciones de lenguaje de programación requieren que los índices de matriz sean enteros. Si la matriz se indexa con números de coma flotante, el compilador debe informar un error.

## **7. Fases de Compilación**

![Fases de compilación](https://drive.google.com/uc?export=view&id=17Dj9ZSrpC1kFe_f9UllBYPhVY27kshCp "Fases de compilación.")

## **8. Diagramas de Estado**

---

Un Diagrama de estado es un método que nos permite ver los estados de un objeto, las transiciones que tendrán sus múltiples estados y el proceso que tendrá dentro de su ciclo de vida antes de continuar.

- Elementos de un diagrama de estados:
  - **Evento:** es una ocurrencia significativa dentro de un proceso, es decir cuándo va a ocurrir algo que haga que el objeto por fin llegue a un estado.
  - **Estado:** Condición de un objeto en un momento determinado de tiempo y que a su vez ejecuta o espera alguna acción es decir lo que a un objeto le pasará dentro de un determinado momento.
  - **Transiciones:** Es la relación entre dos estados, es decir el paso del tiempo o el proceso que llevará a cabo el mismo objeto de un estado a otro.
  - **Transición interna:** Es una transición que permanece en el mismo estado, en vez de involucrar dos estados distintos. Representa un evento que no causa cambio de estado. Se denota como una cadena adicional en el compartimiento de acciones del estado.
  
![Elementos de los Diagramas de Estado](https://drive.google.com/uc?export=view&id=1nKUZkUTcEYbEGkSQxPLSg5FX5mzh52g1 "Elementos de los Diagramas de Estado.")

## **9. Autómatas Finitos**

---

***Autómata:***

Un autómata es un sistema capaz de recibir, tratar y transmitir información, manipulando cadenas de símbolos de salida mediante un conjunto de estados. Acepta señales del medio que le rodea y, como resultado cambia de estado y transmite otras. En cada instante se encuentra en un estado determinado entre varios posibles.

***Autómata Finito:***
> *Un autómata finito tiene un conjunto de estados y su “control” pasa de un estado a otro en respuesta a las “entradas” externas. Una de las diferencias fundamentales entre las clases de autómatas finitos es si dicho control es “determinista”, lo que quiere decir que el autómata no puede encontrarse en más de un estado a un mismo tiempo, o “no determinista”, lo que significa que sí puede estar en varios estados a la vez. (Hopcroft, Motwani, Ullman,2007, 31)*

Un Autómata finito consiste en:

- Un conjunto finito de estados **Q**.
- Un conjunto finito de símbolos de entrada **∑** (alfabeto).
- Un estado inicial **q0**.
- Una función de salida **F**. que asigna a cada par de estado y entrada una salida.
- Una función de transición **𝛿**, que asigna a cada par de estado y entrada un nuevo estado. Esta función:
  - Toma un estado y un símbolo de entrada como argumentos.
  - Regresa un estado.
  - Una "regla" de 𝛿 se escribe como *𝛿(q,a)=p*, donde *q* y *p* son estados y *a* es un símbolo de entrada. Intuitivamente:
    - Si el autómata finito está en un estado *q*, y recibe una entrada *a*, entonces el autómata finito va al estado p(nota: puede ser al mismo estado *q=p*).

![Elementos de un Diagrama de un Autómata Finito](https://drive.google.com/uc?export=view&id=1kgf1win9fdgsNm8yZxMSRAD1C4vKB8Eg "Elementos de un Autómata Finito.")

## **10. Referencias**

- [1]J. Hopcroft, R. Mtwani and J. Ullman, Introducción a la teoría de autómatas, lenguajes y computación (3a. ed.). Madrid: Pearson Educación, 2007.
- [2]A. Parkes, Introduction to languages, machines and logic. London: Springer, 2002.
- [3]J. Frutos Velasco, J. López Sánchez and J. Pérez Díez, Teoría de lenguajes de programación. [Madrid]: [Dep. de Publ. de la Escuela Univers. de Inform. de Madrid].
- [4]P. Isasi Viñuela, P. Martínez Fernández and D. Borrajo, Lenguajes, gramáticas y autómatas. Harlowm: Addison Wesley, 1997.
- [5]J. Elena, Teoría de autómatas y lenguajes formales. Pedro Cid, S.A., 2008.
- [6]"Diagrama de estado - EcuRed", Ecured.cu, 2020. [Online]. Available: <https://www.ecured.cu/Diagrama_de_estado>. [Accessed: 27- Jul- 2020].
- [7]Autómatas Finitos. 2020, pp. 6-7.
