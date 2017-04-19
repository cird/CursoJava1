# Introducción


# Ecosistema del lenguaje
 
Java es un lenguaje interpretado, esto quiere decir que se ejecuta a través de otro programa y no directamente en el sistema. En Java ese otro programa "intérprete" es la JVM (Máquina Virtual Java) y permite correr el mismo programa en diferentes arquitecturas, siempre y cuando el sistema tenga instalada la máquina virtual correspondiente. ¿Por qué se llama máquina virtual y no intérprete? Porque Java requiere que el programa sea compilado antes de ser ejecutable: a diferencia de otros lenguajes interpretados que sí corren tal como fueron escritos (ej. Python, Javascript), la máquina virtual no interpreta el código Java directamente, sino a través de bytecodes que son instrucciones para la JVM generadas por el compilador **javac** (java compiler).

![http://docs.oracle.com/javase/tutorial/figures/getStarted/helloWorld.gif](http://docs.oracle.com/javase/tutorial/figures/getStarted/helloWorld.gif)  
Imagen de http://docs.oracle.com


# Funciones - Operadores

## Funciones

Las funciones describen procesos específicos, utilizan valores de entradas y luego de su ejecución dan como salida resultados (en general en relación con las entradas). Son unos de los bloques básicos para componer un programa. Se invocan simplemente mediante su nombre y entre paréntesis las entradas. Dentro del cuerpo de una función, donde se describe su comportamiento, se puede a su vez invocar a otras funciones, etc...

Por ejemplo al calcular una multiplicación a partir de la entrada de dos números.

```Java
resultado = multiplicar (2,3);
```

Las entradas entre paréntesis y separadas por comas (2,3); son procesadas por la función. Si no admite entradas los paréntesis se ponen vacíos (). Luego de procesar el cálculo obtendremos un resultado, en este caso = 6, valor que se asignará a la variable de la izquierda, es decir, una función después de procesada, es reemplazada por el resultado correspondiente durante el tiempo de ejecución (runtime).

Ejemplo ¿Qué valor se almacena en la variable resultado?

```Java
resultado = multiplicar (multiplicar (2,5), multiplicar (3,5)) ;
```

En este caso se anidan los llamados a función, si reemplazamos cada vez al llamado por su resultado, la función se invoca tres veces y el resultado final es 150. 

Una función puede ser un **productor** de datos, que devuelve resultados sin argumentos de entrada, por ejemplo una función que da la hora; ```obtenerHora()```, o un **consumidor**, que requiere argumentos de entrada pero *no* devuelve resultados, por ejemplo, una función que almacena datos en disco ```guardarDato(dato)``` o imprime en pantalla ```imprimir("hola")```. También hay funciones que no tienen ni entradas, ni salidas, y simplemente realizan una **acción** ejecutable, por ejemplo una subrutina para esperar un tiempo fijo ```esperarUnSegundo()```, su efecto es ocupar el procesador por un tiempo.

![funciones.png](funciones.png)

## Efectos secundarios

Si al ejecutar una función ocurren cambios por fuera de la relación entrada/salida se dice que tiene *efectos secundarios* o *colaterales* es decir que modifican el estado del sistema, pueden afectar variables internas, o dispositivos de salida. Por ejemplo la función ```imprimirEnPantalla("algo")``` producirá cambios en la pantalla.

Una función que no produce efectos secundarios, y además es coherente, es decir, sólo produce resultados iguales para entradas iguales, se llama función *pura*, aunque en la práctica todas las funciones tienen "efectos secundarios" ya que todas consumen energía y tiempo para ejecutarse, lo cual produce cambios en el sistema y en el ambiente. El nombre "función pura" se usa en referencia al estado lógico del sistema. 
  
## Cómo escribir una función 

Para definir una función en Java primero se declara el **tipo de dato del resultado**, si no devuelve nada se declara como **void**; luego se escribe el **nombre de la función**; y finalmente la **lista de parámetros de entrada**, cada entrada con su tipo correspondiente, todas entre paréntesis y separadas por coma. 


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
O la misma función de manera más sencilla 

```Java
int sumar( int a, int b){        
        return a+b;
}
```

El cuerpo de la función es la descripción del proceso que realiza y se escribe entre llaves **{ }** que sirven para demarcar bloques de código. En este caso como la función devuelve un valor necesita invocar la sentencia **return** que especifica cuál es el valor que la función va a devolver como resultado. 

Hay una función especial, cuyo nombre está reservado: la función **main**. A diferencia de las demás funciones que para invocarlas hay que poner el nombre y los argumentos en el programa, a la función **main** no hace falta llamarla, basta con que esté implementada y será llamada automáticamente por el sistema al arrancar el programa. Es la primera función que se ejecuta. Puede haber varias funciones main en un programa pero solo una se elegirá como punto de arranque, *entry point*. Dentro la función main se pueden escribir llamados a demás funciones, sentencias y expresiones.

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
Las expresiones son combinaciones de operadores, llamados a función y/o asignaciones, y forman parte de las *sentencias* de un programa.
Las sentencias son las "unidades" del programa. En Java terminan cada una en punto y coma ";" y están compuestas de una o más expresiones. Ejemplo:

```Java
log.info("un mensaje");

```

Las sentencias se pueden agrupar en bloques que definen además un alcance para las variables. 

# Tipos de datos Primitivos:

No se recomiendan en general, pero aún pueden/deben usarse en casos especiales extremadamente simples o muy específicos.

### short
Permite almacenar un valor entero con signo de 16-bit desde -32768 a hasta 32767 inclusive. 
### int
Por default permite un valor entero con signo de 32-bit de -2^31 and a maximum value of 2^31-1. 
### long
Por default permite un valor entero con signo de 64-bit de -2^63 a 2^63-1. 
### float
Permite almacenar valores con coma flotante de precisión simple, formato 32-bit IEEE 754
### double
Permite almacenar valores con coma flotante de precisión doble, formato 64-bit IEEE 754 
### boolean
Puede almacenar un valor, de solo dos posibles: true o false. 
### byte
Almacena un valor entero de 8-bit, desde -128 and a hasta 127 inclusive. 
### char
Permite almacenar un valor Unicode de 16-bit desde  '\u0000' (or 0) a '\uffff' 65535.

Todos los tipos numéricos primitivos son con signo, lamentablemente en java todos tienen signo, el formato es en complemento a dos (la representación binaria internat de los negativos es como la de un positivo pero invirtiendo todos los bits y sumando uno, esto facilita internamente algunas operaciones comunes). Desde Java 8 se proveen algunas funciones para tratar int y long como si fueran sin signo.


# Tipo String

Los Strings, o cadenas de caracteres, no son un tipo básico pero tienen facilidades para crearlos como si lo fueran. Internamente una vez creada una variable String no puede modificarse, o mejor dicho, cuando se modifica un String internamente se crea otra variable nueva.
 
 ```Java
 String texto = "Esta es una variable que almacena texto";
 System.out.println(texto);
 ```
