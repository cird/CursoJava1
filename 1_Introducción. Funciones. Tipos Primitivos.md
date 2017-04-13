# Introducción


# Ecosistema del lenguaje
 
Java es un lenguaje interpretado, esto quiere decir que se ejecuta a través de otro programa y no directamente en el sistema, ese otro programa, el intérprete, en este caso es la máquina virtual java (JVM) que permite correr el mismo programa Java en diferentes arquitecturas, siempre que el sistema tenga instalada la máquina virtual correspondiente. ¿Por qué se llama máquina virtual y no intérprete? porque un programa en Java requiere compilación antes de ser ejecutable, a diferencia de otros lenguajes interpretados que sí corren tal como fueron escritos (ej. Python, Javascript), la máquina virtual no interpreta el código Java directamente, sino a través de los bytecodes que son instrucciones para la JVM generadas por el compilador **javac**(java compiler).

![http://docs.oracle.com/javase/tutorial/figures/getStarted/helloWorld.gif](http://docs.oracle.com/javase/tutorial/figures/getStarted/helloWorld.gif)  
Imagen de http://docs.oracle.com


# Funciones, Operadores

3.1 Funciones

Las funciones describen procesos específicos, utilizan valores de entradas y luego de su ejecución dan como salida resultados (en general en relación con esas entradas), son uno de los bloques básicos para componer un programa. Se invocan simplemente mediante su nombre y las entradas entre paréntesis, pudiendo ser utilizadas desde otras funciones, las cuales a su vez pueden invocar a otras, etc..

Por ejemplo al calcular una multiplicación a partir de la entrada de dos números.
```Java
resultado = multiplicar (2,3);
```

Las entradas se ingresan entre paréntesis y separadas por comas (2,3); si una función no admite entradas los paréntesis se ponen vacíos (). Luego de procesar ese cálculo obtendremos resultado, en este caso = 6, que se asignará el valor a la variable de la izquierda, es decir, después de procesada, es reemplazada por su resultado correspondiente en tiempo de ejecución (runtime), además de otros *efectos secundario* que pueda tener la función.

Otro ejemplo ¿Qué valor se almacena en la variable resultado?

resultado = multiplicar (multiplicar (2,5), multiplicar (3,5)) ;

En este caso se anidan los llamados a función, si reemplazamos cada vez, cada llamado por su resultado, la función se invoca tres veces y el resultado final es 150. 

Una función podría ser un **productor** de datos, devolviendo resultados sin requerir argumentos de entrada, por ejemplo una función que da la hora; podría ser un **consumidor**, que requiere argumentos de entrada pero no devuelve resultados, por ejemplo una función que imprime en pantalla algún valor ingresado ( en este caso aunque no devuelve explícitamente algo sin embargo acciona la escritura del texto en pantalla, esto ocurre como un *efecto secundario*, el cual en este caso es intencional pero sucede por fuera de la relación entrada/salida, es decir, el resultado no queda en el programa sino que va a parar a la pantalla, que es un periférico de salida, obviamente fuera del programa), finalmente puede haber funciones que no requieren ni entradas, ni devuelven salidas, que simplemente realizan una **acción** ejecutable, por ejemplo una subrutina para esperar un tiempo fijo esperarUnSegundo(), que su efecto es ocupar el procesador por un tiempo.
  
Para definir una función en Java primero se declara el **tipo de dato del resultado** (si no devuelve nada se declara como **void**), luego se escribe el **nombre de la función**, y finalmente la **lista de parámetros de entrada** cada una de las entradas con su tipo correspondiente, entre paréntesis y separados por coma. 


```Java
int multiplicar( int a, int b) { 
    return a * b ;
}
```

```Java
int sumar( int a, int b){
        int result;        
        result = a+b;        
        return resultado;
}
```
O la misma de manera más sencilla 

```Java
int sumar( int a, int b){        
        return a+b;
}
```


El cuerpo de la función es la descripción del proceso que realiza, y se escribe entre llaves **{ }** que sirven para demarcar bloques de código. En este caso como la función devuelve un valor necesita invocar la sentencia **return** que especifica cuál es el valor que la función va a devolver como resultado. 

Hay una función especial, cuyo nombre está reservado: la función **main**. A diferencia de las demás funciones, que para invocarlas hay que poner el nombre y los argumentos en el programa, a la función **main** no hace falta llamarla, basta con que esté implementada y será llamada automáticamente por el sistema al arrancar el programa ( puede haber varias funciones main en un programa pero solo una se elegirá como punto de arranque), es la primer función que se ejecuta, dentro la función main se pueden escribir llamados a demás funciones, sentencias y expresiones.

```Java
public static void main(String args[]){	
 	//aquí va el cuerpo del programa principal
}
```

```Java
public class Test { 
    public static void main(String[] args) {
        System.out.println("Hola mundo!"); 
    }
}
```

# Expresiones, Sentencias y Bloques
Las expresiones son combinaciones de operadores, llamados a función, asignaciones, y forman parte de las sentencias de los programas, que son las unidades del programa, en Java terminan cada una en punto y coma ";" y están compuesta de una o más expresiones. Ejemplo

```Java



```

Las sentencias pueden agruparse en bloques que además definen un alcance para las variables. 

# Tipos de datos Primitivos:

### short:
Permite almacenar un valor entero con signo de 16-bit desde -32768 a hasta 32767 inclusive. 
### int:
Por default permite un valor entero con signo de 32-bit de -2^31 and a maximum value of 2^31-1. 
### long:
Por default permite un valor entero con signo de 64-bit de -2^63 a 2^63-1. 
### float:
Permite almacenar valores con coma flotante de precisión simple, formato 32-bit IEEE 754
### double:
Permite almacenar valores con coma flotante de precisión doble, formato 64-bit IEEE 754 
### boolean:
Puede almacenar un valor, de solo dos posibles: true o false. 
### byte: 
Almacena un valor entero de 8-bit, desde -128 and a hasta 127 inclusive. 
### char:
Permite almacenar un valor Unicode de 16-bit desde  '\u0000' (or 0) a '\uffff' 65535.

Todos los tipos numéricos primitivos son con signo, lamentablemente en java todos tienen signo, el formato es en complemento a dos (la representación binaria internat de los negativos es como la de un positivo pero invirtiendo todos los bits y sumando uno, esto facilita internamente algunas operaciones comunes). Desde Java 8 se proveen algunas funciones para tratar int y long como si fueran sin signo.

No se recomiendan usar. Aún pueden usarse en casos especiales extremadamente simples o muy específicos.


# Tipo String

Los Strings, o cadenas de caracteres, no son un tipo básico pero tienen facilidades para crearlos como si lo fueran, internamente una vez creada una variable String no puede modificarse, o mejor dicho, cuando se modifica un String internamente se crea otra variable nueva.
 
 ```Java
 String texto = "Esta es una variable que almacena texto";
 System.out.println(texto);
 ```
