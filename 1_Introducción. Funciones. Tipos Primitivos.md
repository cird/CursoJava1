# Introducción


# Ecosistema del lenguaje
 
Java es lenguaje **interpretado**, se ejecuta *a través de otro programa* intérprete y no directamente en el sistema. En Java ese *otro programa* es la JVM (Máquina Virtual Java) que permite correr el mismo programa en diferentes arquitecturas, siempre que el sistema tenga instalada la JVM. ¿Por qué se llama máquina virtual y no intérprete? Porque Java requiere que el programa sea compilado antes de ser ejecutable: a diferencia de otros lenguajes interpretados que corren tal como fueron escritos (ej. Python, Javascript), la máquina virtual no interpreta el código de archivos .java directamente, sino el programa se compila en códigos llamados bytecodes que son las instrucciones de la JVM generadas por el compilador **javac** (java compiler) en archivos .class o .jar.

<p align="center"> 
.java => .jar => jvm => sistema
</p>

<p align="center"> 
<img src="http://docs.oracle.com/javase/tutorial/figures/getStarted/helloWorld.gif">
</p>
Fuente https://docs.oracle.com/javase/tutorial/


# Funciones - Operadores

## Funciones

Las funciones describen procesos específicos, utilizan valores de entradas y luego de su ejecución dan como salida resultados. Son unos de los bloques básicos para componer un programa. Se invocan simplemente mediante su nombre y entre paréntesis las entradas. Implementarla es escribir el cuerpo de la función, describir paso a paso su comportamiento, el cual puede a su vez necesitar invocar a otras funciones, etc...

Por ejemplo calcular una multiplicación con la entrada de dos números.

```Java
resultado = multiplicar (2,3);
```

Las entradas entre paréntesis y separadas por comas (2,3) son procesadas por la función. Si no admite entradas los paréntesis van vacíos (). Luego de procesar el cálculo da un resultado, en este caso = 6, ese valor se asigna a la variable de la izquierda, una función cuando termina de ser procesada es reemplazada por el resultado correspondiente durante el tiempo de ejecución (runtime).

Ejemplo ¿Qué valor se almacena en la variable **resultado**?

```Java
resultado = multiplicar (multiplicar (2,5), multiplicar (3,5)) ;
```

En este caso se anidan los llamados a función, la función se invoca tres veces y el resultado final es 150.

Una función puede ser un **productor** de datos, devuelve resultados sin argumentos de entrada, ejemplo una función que da la hora; ```obtenerHora()```, puede ser un **consumidor**, que requiere entradas pero *no* devuelve resultados, ejemplo una función para imprimir en pantalla ```imprimir("hola")```, o pueden no tener ni entradas, ni salidas, solo realizan una **acción** ejecutable, ejemplo una subrutina para esperar un tiempo fijo ```esperarUnSegundo()```, su efecto es ocupar el procesador por un tiempo.

<p align="center"> 
<img src="funciones.png">
</p>

### Operadores

Ciertas funciones básicas ya vienen incorporadas en el lenguaje como "operadores", que pueden tener una entrada (unarios), dos entradas (binarios), tres entradas (ternarios). Ejemplos de operadores unarios, el operador NOT, para negación lógica (**!**), o el operador NOT para inversión bit a bit (**~**). Ejemplos de operadores binarios: la suma (**+**), la multiplicación (**\***), la división (**/**), el módulo o resto de la división(**%**), las comparaciones (**<**,**>**,**<=**,**>=**,**==**). Finalmente el operador (**?**) es un ejemplo de operador *ternario* para hacer asignaciones condicionales como ``` estado = (temperatura>30)?"caliente":"frío"; ``` si la variable temperatura es mayor a 30, la variable estado se asigna "caliente", sino se le asigna "frio".

## Efectos secundarios!

Si al ejecutar una función ocurren cambios por fuera de la relación entrada/salida se dice que tiene *efectos secundarios* o *colaterales* que modifican el estado del sistema y pueden afectar variables internas o dispositivos de salida. Ejemplo la función ```imprimirEnPantalla("algo")``` producirá como efectos secundarios los cambios en la pantalla.

Si una función no produce efectos secundarios y además es coherente es decir que sólo produce resultados iguales para entradas iguales, se llama función *pura*, aunque en la práctica todas las funciones tienen "efectos secundarios" ya que todas consumen energía y tiempo para ejecutarse, y estos son cambios en el sistema y en el ambiente, se usa el nombre "función pura" en referencia al estado lógico del sistema: valores en memoria y en disco. 
  
## Cómo escribir una función 

Para escribir una función en Java primero se declara el **tipo de dato del resultado**; luego el **nombre de la función**; y finalmente la lista de **parámetros de entrada**, cada entrada indicando el tipo de dato correspondiente, todas entre paréntesis y separadas por coma. (*si no devuelve resultado se declara como **void**)



```Java
int multiplicar( int a, int b) { 
    return a * b ;
}
```

```Java
int sumar( int a, int b){
        int result;        
        result = a+b;        
        return result;
}
```
O la misma función de manera más sencilla 

```Java
int sumar( int a, int b){        
        return a+b;
}
```

```Java
void saludar() { 
    System.out.println("Hola");
}
```

El contenido, llamado cuerpo de la función va en un bloque de código entre llaves **{ }**, ahí se describe el proceso que realiza. Si la función devuelve un valor se necesita invocar la palabra clave **return** con la que se especifica el valor que devuelve como resultado. 

Hay una función con nombre reservado para uso especial: la función **main**. A diferencia de las demás que para invocarlas hay que poner el nombre y argumentos en el programa, a la función **main** no hace falta llamarla, alcanza con que esté implementada y será llamada automáticamente por el sistema al arrancar el programa. Es la primera función que se ejecuta. Aunque hubiera varias funciones main en un programa solo una se elegirá como punto de arranque o *entry point*. Dentro de la función main se inicia el programa, se hacen llamados a otras funciones, sentencias y expresiones, etc.

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
Las sentencias son las "unidades" del programa. En Java terminan cada una en punto y coma ";" y están compuestas de una o más expresiones. Podríamos decir es cada línea de código aunque algunas sentencias pueden ocupar más de una línea. Las expresiones son las combinaciones de asignaciones, llamados a función, operadores, que forman parte de las *sentencias* del programa.

Ejemplo:

```Java
log.info("un mensaje");

```

Las sentencias se pueden agrupar en bloques que además definen el *alcance* para las variables.

# Tipos de datos Primitivos:

No se recomiendan en general, pero aún pueden/deben usarse en casos especiales extremadamente simples o muy específicos.

### short
Permite almacenar un valor entero con signo de 16-bit desde -32768 a hasta 32767 inclusive. 
### int
Por default permite un valor entero con signo de 32-bit desde -2^31 hasta 2^31-1. 
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

En Java todos los tipos numéricos primitivos son con signo, el formato es en complemento a dos (la representación binaria interna de los negativos es como la de un positivo pero invirtiendo todos los bits y sumando uno, esta representación facilita internamente algunas operaciones comunes). Desde Java 8 se proveen funciones para tratar **int** y **long** como si fueran sin signo, esto es trabajar con los bits raw (crudos) sin interpretar ningún bit como signo.


# Tipo String

Los Strings, o cadenas de caracteres, no son un tipo básico pero Java provee facilidades para crearlos como si lo fueran. Internamente una vez creada una variable String no puede modificarse, o mejor dicho, modificar un String internamente es crear otra variable nueva.
 
 ```Java
 String texto = "Esta es una variable que almacena texto";
 System.out.println(texto);
 ```
