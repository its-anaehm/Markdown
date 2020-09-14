# Conceptos Basicos de Programación en Bash

## Comentarios

---

**Comentarios de una linea:**

Los comentarios de una linea en Bash se generan colocando una almohadilla (numeral -> #) al inicio de la linea:

        #Este es el ejemplo de un comentario.

**Comentarios de múltiples lineas:**

Los comentarios de multiples lineas en Bash se generan de la siguiente manera:

        : ' 
            Esto es un comentario
            de multiples lineas
            en Bash
        '

> **NOTA:** " **#!** -> **Hashbang** indica donde está el archivo, en este caso el interprete de bash y se coloca al inicio de los programas."

---

## Generación de mensajes de salida

---

**echo:**

***echo*** es la función que permite imprimir en pantalla.

***Ejemplo:*** Programa que despliegue en consola la frase "Hola Mundo."

    Programa1.sh:
        #!/bin/bash
        echo "Hola mundo."




    Despliegue en consola: 
        Hola mundo.

---

## Asignaciones

---

**Variables de programación con Bash:**

En bash no se declara el tipo de variable pero puede ser un número, letra o cadena de caracteres.

> **Declaración de una variable:** nombre_variable=valor_variable

Para recuperar el valor de dicha variable sólo hay que anteponer el símbolo de dolar $ antes del nombre de la variable:

> $nombre_variable

***Nombre de las variables***

Las variables pueden tomar prácticamente cualquier nombre, sin embargo, existen algunas restricciones:

Sólo puede contener caracteres alfanuméricos y guiones bajos

* El primer carácter debe ser una letra del alfabeto o “_” (este último caso se suele reservar para casos especiales).
* No pueden contener espacios.
* Las mayúsculas y las minúsculas importan, “a” es distinto de “A”.
* Algunos nombres som usado como variables de entorno y no los debemos utilizar para evitar sobrescribirlas (e.g.,PATH).

De manera general, y para evitar problemas con las variables de entorno que siempre están escritas en mayúscula, deberemos escribir el nombre de las variables en minúscula.

***Ejemplo:*** En este programa se ejemplifica la forma de asignar variables, hacer el llamado a una variable y mostrar el contenido de una variable.

    Programa2-1.sh:
        #!/bin/bash
        #Asignación de una variable
        hola = 1
        #Llamado a una variable
        $hola
        #Mostrando el contenido de la variable en consola
        echo $hola




    Despliegue en consola:
        1

> **NOTA:** "**$**" Con el símbolo de dolar se hace el llamado a una variable para retornar su valor.
---
***Cadenas:***

---
Bash tiene un modesto control de cadenas aunque en muchos scripts puede ser mucho más que interesante y en ocasiones muy útil.

**Manipulación de cadenas de texto:**

*Extraer subcadena:*

Mediante ${cadena:posicion:longitud} podemos extraer una subcadena de otra cadena. Si omitimos :longitud, entonces extraerá todos los caracteres hasta el final de cadena.

Por ejemplo en la cadena string=abcABC123ABCabc:

* echo ${string:0} : abcABC123ABCabc
* echo ${string:0:1} : a (primer caracter)
* echo ${string:7} : 23ABCabc
* echo ${string:7:3} : 23A (3 caracteres desde posición 7)
* echo ${string:7:-3} : 23ABCabc (desde posición 7 hasta el final)
* echo ${string: -4} : Cabc (atención al espacio antes del menos)
* echo ${string: -4:2} : Ca (atención al espacio antes del menos)

***Ejemplo:*** Programa que asigna una cadena a una variable y retorna varios componentes que se obtienen de dicha cadena

    Programa2-2.sh:
        # Cadena de ejemplo:
        string=123.abc.456.ABC.123

        # Ver la longitud de la cadena
        $ echo ${#string}
        19

        # Extraer subcadena desde una posicion
        $ echo ${string:4}
        abc.456.ABC.123

        # Extraer subcadena de longitud determinada
        # desde una posicion
        $ echo ${string:4:7}
        abc.456

        # Eliminar la cadena coincidente del principio de la cadena
        $ echo ${string#123}
        .abc.456.ABC.123

        # Eliminar la cadena coincidente del final de la cadena
        $ echo ${string%123}
        123.abc.456.ABC.

        # Reemplazar la primera aparación de una subcadena en la cadena
        $ echo ${string/123/QWE}
        QWE.abc.456.ABC.123

        # Reemplazar todas las apariciones de una subcadena en la cadena
        $ echo ${string//123/QWE}
        QWE.abc.456.ABC.QWE

        # Reemplazar si hay coincidencia al pricipio o al final de la cadena:
        $ echo ${string/#123/QWE}
        QWE.abc.456.ABC.123

        $ echo ${string/%123/QWE}
        123.abc.456.ABC.QWE

        # Longitud de la coincidencia al principio de la cadena (dos formas)
        $ expr match "$string" '123'
        3
        $ expr "$string" : '123'
        3
---
**Booleanos:**

---
***Ejemplo:*** En este programa se ejemplifica la forma de trabajar con booleanos en Bash (Ya que no se declaran tipos de variables en Bash se pueden hacer verificaciones a traves de valores o cadenas de texto como se ve en el ejemplo).

    Programa2-3.sh:
        #!/bin/bash
        #Declarando la variable 
        bool=true
        #Corroborando por medio de su valor
        if [ $bool = true ]; then
            echo "Es verdadero"
        fi
        #Corroborando por medio de una cadena
        if [ $bool = "true" ]; then
            echo "Es verdadero"
        fi




    Despliegue en consola:
        Es verdadero
        Es verdadero

---
***Números:**

---
Por defecto, una variable, en cualquier script en Bash, con independencia de su contenido, es tratada como una cadena de texto, y no como un número. Esto, como te puedes imaginar, complica esto de las operaciones matemáticas. Así, en primera instancia podrías pensar que es mejor utilizar algún otro lenguaje de programación para estos menesteres. Sin embargo, no es necesario, con el paso de las versiones de Bash, poco a poco, se ha ido mejorando.

Sin embargo, una observación importante, Bash solo opera con enteros. Para realizar operaciones matemáticas en Bash con números reales, necesitas utilizar bc.

Así básicamente tienes hasta cinco opciones, al menos, para facilitarte el trabajo con las operaciones matemáticas. Se trata de **declare**, **expr**, **let**, dobles paréntesis y bc tal y como te he adelantado en el párrafo anterior.

**DECLARE:**

La primera de las opciones que tienes para realizar operaciones matemáticas es declare. Así, con declare defines algunas propiedades de la variable.

-r define la variable como de solo lectura. Es decir, que tu variable es inmutable, de forma que si intentas cambiar su valor te arrojará un error.

-i te permite declarar la variable como un entero.

-a lo utilizarás para declarar arrays.

-f te permite declarar una función. Además si ejecuta declare -f, así sin argumentos, obtendrás un listado de las funciones declaradas previamente.

Una observación importante es que al definir una variable con declare estás restringiendo su ámbito a la función donde lo hayas declarado. Es decir, básicamente es como si utilizas local.

**EXPR:**

La segunda de las opciones para realizar operaciones matemáticas en Bash es utilizando expr. Se trata de un antigua aplicación de Unix, utilizada cuando Bourne Shell, no soportaba operaciones matemáticas. Sin embargo, hoy por hoy no tiene tanto sentido su uso. Ten en cuenta que necesitarás espacios entre los operandos y el operador. Así por ejemplo, echo $(expr 1+1) te devolverá 1+1, mientras que echo $(expr 1 + 1) te devolverá, como esperas, 2.

    echo $(expr 5 \* 5) 
devuelve 25, y si, hay que escapar el signo de multiplicación.

    d=1;echo $(expr $d + 1 ) 
devuelve 2.

**LET:**

Otra opción para realizar operaciones matemáticas es let. let evalua cada argumento como una expresión aritmética. Las operaciones se evaluan como enteros, mientras que una división por cero arrojará un error.

De nuevo, las cosas se ven mas claras con unos ejemplos,

    let z=25; echo $z 
Devuelve 25

    let z++; echo $z 
Devuelve 26

    let z=z+10; echo $z. 
Devuelve 36

**DOBLES PARÉNTESIS:**

Otra opción para realizar operaciones matemáticas, es el uso de los dobles paréntesis. Al fin y al cabo, los dobles paréntesis se comportan como let que acabas de ver. Aunque tienen la ventaja de que un doble paréntesis puede incluir a otro doble paréntesis. De esta manera, los ejemplos que te he indicado para let se pueden hacer exactamente igual para el caso de los dobles paréntesis,

    ((z=25)); echo $z 
Devuelve 25

    ((z++)); echo $z 
Devuelve 26

    ((z=z+10)); echo $z
Devuelve 36

Pero además, si quieres devolver el resultado de una operación simplemente tienes que preceder el doble paréntesis con $, es decir, puedes simplificar los ejemplos anteriores de la siguiente manera,

    echo $((z=25)); 
Devuelve 25

    echo $((z++)); 
Devuelve 26

    echo $((z=z+10));
Devuelve 36

Esto ta va a permitir, como se ha adelantado anteriormente, incluir una operación matemática dentro de otra. Por ejemplo,

`echo $((25 + $((5+5))))
o incluso echo $((25 + $((diez=5+5))));echo $diez

***MATEMÁTICAS EN BASH CON BC***

---
Todas las operaciones matemáticas realizadas hasta el momento solo implican números enteros. Sin embargo, ¿que sucede cuando quieres realizar operaciones matemáticas con números reales?. En este caso necesitarás recurrir a una herramienta como es bc.

*bc* es una herramienta que funciona exactamente como una calculadora matemática. Tu le pasas una serie de operaciones, y esta herramienta se encarga de evaluarla.

Ejemplos

    echo '4.1+5.2' | bc 
Devuelve 9.3

    echo '4.1*5.2' | bc 
Devuelve 21.3

Si quieres guardar el resultado de la operación en una variable, tienes que modificar los ejemplos anteriores como sigue,

    z=$(echo '4.1+5.2' | bc);echo $z 
Devuelve 9.3

    z=$(echo '4.1*5.2' | bc);echo $z 
Devuelve 21.3

También es posible definir variables. Sin embargo, estas variables son locales a bc, es decir, luego no las vas a poder utilizar fuera de la expresión que le has pasado a la herramienta bc. Es decir,

    echo 'var=10;var++;var' | bc 
Devolverá 11. Sin embargo si ejecutas echo $var no obtendrás valor alguno.

---

## Estructuras de control de Flujo

---

Condicional

**If:**

La sintaxis básica de un condicional es la siguiente

    if [[ CONDICIÓN ]];
    then
        COMANDO 1 si se cumple la condición
    fi

También se puede especificar qué hacer si la condición no se cumple:

    if [[ CONDICIÓN ]];
    then
        COMANDO 1 si se cumple la condición
    else
        COMANDO 2 si no se cumple la condición
    fi

Incluso se pueden añadir más condiciones concatenando más if:

    if [[ CONDICIÓN 1 ]];
    then
        COMANDO 1 si se cumple la condición 1
    elif [[ CONDICIÓN 2 ]];
    then
        COMANDO 2 si se cumple la condición 2
    else
        COMANDO 3 si no se cumple la condición 2
    fi

---
    Programa3-1.sh
        #!/bin/bash
        if [ "UBUNTU" = "UBUNTU" ]; then
            echo "Son iguales"
        else
            echo "Son distinos"
        fi




    Despliegue en consola:
        Son iguales

---
    Programa3-2.sh
        #!/bin/bash
        Word1="UBUNTU"
        Word2="UBUNTU2"
        if [ "$Word1" = "$Word2" ]; then
            echo "Son iguales"
        else
            echo "Son distinos"
        fi





    Despliegue en consola:
        Son distintos

---
    Programa3-3.sh
        #!/bin/bash
        Word1="UBUNTU"
        Word2="UBUNTU2"
        Word3="UBUNTU"
        if [ "$Word1" = "$Word2" ]; then
            echo "1 y 2 son iguales"
        elif [ "$Word1" = "$Word3" ]; then
            echo "1 y 3 son iguales"
        else
            echo "Son distinos"
        fi




    Despliegue en consola:
        1 y 3 son iguales

Bucles

**for:**

La sintaxis general de los bucles es la siguiente:

    for VARIABLE in LISTA_VALORES;
    do
        COMANDO 1
        COMANDO 2
        ...
        COMANDO N
    done

---

    Programa4-1.sh
        #!/bin/bash
        for((i=1; i<=10; i++)):
        do
            echo $i
        done




    Despliegue en consola:
        1
        2
        3
        4
        5
        6
        7
        8
        9
        10

---
    Programa4-2.sh
        #!/bin/bash
        Lista="1 2 3"
        for i in $Lista:
        do
            echo "Se imprime el $i"
        done




    Despliegue en consola:
        1
        2
        3

---
    Programa4-3.sh
        #!/bin/bash
        Lista="UBUNTU 2 LLP 3 IS"
        for i in $Lista:
        do
            echo "Se imprime el $i"
        done




    Despliegue en consola:
        UBUNUT
        2
        LLP
        3
        IS

**While:**

    Programa5.sh
        #!/bin/bash
        Contador=0
        while [ $contador -lt 10]:
        do
            echo "Se imprime el $Contador"
            let contador = contador+1
        done




    Despliegue en consola:
        0
        1
        2
        3
        4
        5
        6
        7
        8
        9

**Until:**

    Programa6.sh
        #!/bin/bash
        Contador=0
        while [ $contador -gt 10]:
        do
            echo "Se imprime el $Contador"
            let contador = contador+1
        done




    Despliegue en consola:
        0
        1
        2
        3
        4
        5
        6
        7
        8
        9
        10

> **NOTA:** ***Until*** es un bucle como While y ***let*** se utiliza para tomar a contador como un número.

---

## Operadores Lógicos

---

Los Operadores lógicos para trabajar con valores alfanuméricos son:

| Operador | Evaluación |
|--- |--- |
| = | Igual a |
| != | Diferente de |
| > | Mayor que en orden ASCII |
| < | Menor que en orden ASCII |
| -n | La cadena no esta vacía |
| -z | La cadena esta vacía |

***Ejemplo:*** Programa para practicar con distintos operadores para valores alfanuméricos (cambie el operador lógico del condicional para poder contemplar los distintos resultados).

    Programa7.sh
        #!/bin/bash
        cadena1="a"
        cadena2="b"
        if [ "$cadena1" = "$cadena2" ]; then
            echo "Verdadero"
        else
            echo "Falso"
        fi




    Despliegue en consola:
        Falso

Los Operadores lógicos para trabajar con valores numéricos son:

| Operador | Evaluación |
|--- |--- |
| -lt | Mayor que |
| -le | Menor que |
| -eq | Igual |
| -ge | Mayor o igual que |
| -gt | Mayor que |
| -ne | Diferente |

***Ejemplo:*** Programa para practicar con distintos operadores para valores numéricos (cambie el operador lógico del condicional para poder contemplar los distintos resultados).

    Programa7.sh
        #!/bin/bash
        let numero1=1
        let numero2=2
        if [ "$numero1" -ne "$numero2" ]; then
            echo "Verdadero"
        else
            echo "Falso"
        fi




    Despliegue en consola:
        Verdadero

---

## Declaración y Ejecución de Funciones

---

Declaración de una función:

    function <nombre de la función> {
        #Contenido de la función
    }

***Ejemplo:*** Para una función que devuelve el mensaje "Hola Mundo."

    Programa8.sh
        #°/bin/bash
        #Función
        function saludo {
            echo "Hola Mundo."
        }
        #Llamado a la fucnión
        saludar




        Despliegue en consola:
            Hola Mundo.

***Ejemplo:*** Para una función con parametros."

    Programa9.1.sh
        #°/bin/bash
        #Función
        function saludo {
            #$0
            echo $1
            echo $2
        }
        #Llamado a la fucnión con parametros, los cuales deben de estar separados por un espacio.
        saludar Hola Mundo.





        Despliegue en consola:
            Hola 
            Mundo.

>**NOTA:** Si ingresamos el parámetro ***$0*** en una fución está nos retornara el nombre del archivo von el que estamos trabajando.
