# Introducción


# Ecosistema del lenguaje.
 
Java es un lenguaje interpretado, esto quiere decir que se ejecuta a través de otro programa y no directamente en el sistema, en este caso ese otro programa es la máquina virtual java (JVM), esto permite correr el programa en diferentes arquitecturas, siempre que tengan instalada la máquina virtual correspondiente. ¿Por qué se llama máquina virtual y no intérprete? porque un programa en Java antes de ejecutarse requiere compilación, a diferencia de otros lenguajes interpretados la máquina virtual no interpreta el código Java sino que ejecuta el código compilado en bytecodes que son instrucciones de la JVM, intermediaria entre el código compilado Java y el sistema en cuestión.

![http://docs.oracle.com/javase/tutorial/figures/getStarted/helloWorld.gif](http://docs.oracle.com/javase/tutorial/figures/getStarted/helloWorld.gif)  
Imagen de http://docs.oracle.com


# Funciones, Operadores

```Java
int suma( int a, int b){
        int result;        
        result = a+b;        
        return resultado;
}
```
O más sencilla 

```Java
int suma( int a, int b){        
        return a+b;
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
