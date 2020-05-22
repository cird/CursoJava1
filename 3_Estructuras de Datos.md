## Variables y Alcance

#### Variables 
  - **de instancia**, pertenecen a objetos  
  - **de clase**, valen para toda la clase, se declaran como ***static***  
  - **locales**, son de uso interno de una función o bloque.  
  - **parámetros**, son las usadas en los argumentos de una función.  


## Estructuras de datos.


#### Arreglo

El arreglo/array es un objeto contenedor básico para un conjunto ordenado de valores fijos de un mismo tipo. La cantidad de elementos del arreglo es fija y se establece al momento que se crea. Los **arrays** en Java no son tipos primitivos sino de referencia, por lo tanto no pueden copiarse mediante asignación, tienen además la propiedad **length** que contiene la cantidad de elementos del array.


```Java
int[] arreglo = new int[10];

System.out.println(" Tamaño array : " + arreglo.length);
```
<p align="center">
    <img src="array.gif">
</p>

fuente: https://docs.oracle.com/javase/tutorial/

#### Set/Conjunto
Set es un conjunto (desordenado) de objetos que no se repiten. Usualmente para manejar este tipo de objetos se tienen métodos/funciones que permiten saber si un objeto está o no en el Set.

Java provee por ejemplo la clase ```java.util.HashSet``` que permite conjuntos de objetos de cualquier tipo.

#### Lista/List
Una lista es una colección de datos ordenados, una secuencia de objetos, la lista está ordenada y cada objeto tiene una posición definida, es decir, internamente se pueden repetir pero la *clave* que identifica a cada objeto es un número único.

Java provee por ejemplo la clase ```java.util.ArrayList``` que permite armar listas con objetos de cualquier tipo.

#### Diccionario/Map 
Un diccionario o mapa es una estructura de datos que asocia claves con valores, se puede pensar como una tabla de dos columnas, donde la primera indica las claves y la segunda los valores. En general se implementar con tablas hash, lo cual significa que internamente usa un código breve (hash) que se calcula por cada claves lo cual permite operaciones más rápidas.

Java provee la clase ```java.util.HashMap``` que permite realizar tablas de clave-valor con objetos de cualquier tipo.

#### Pila/Stack
Una pila o stack es una estructura de datos del tipo last-in-first-out (LIFO), es decir, el último en entrar es el primero en salir, como en una pila de platos o de libros, se retiran en la secuencia inversa que se apilan. Permite entonces tener un orden específico de la insersión y extracción de datos. 

Normalmente las implementaciones incluyen a las funciones : **push** para insertar un objeto y **pop** para extraerlo.

Java provee la clase ```java.util.Stack``` que permite realizar pilas con objetos de cualquier tipo.

#### Cola/Queue

Una cola o queue es una estructura de datos del tipo first-in-first-out (FIFO), es decir, el primero en entrar es el primero en salir, como una cola de espera. Permite un orden estricto para insertar y extraer los datos. 

Normalmente las implementaciones incluyen a las funciones **push** para insertar un objeto y **pop** para extraerlo.

Java provee la *interface* ```java.util.Queue``` que implementada en clases como LinkedList permite crear colas de objetos.


#### Package

Un **espacio de nombres** es un contexto donde los nombres son únicos, por ejemplo en una carpeta no puede haber archivos con el mismo nombre, tienen que ser diferentes o estar en carpetas diferentes. En Java la jerarquía más alta del espacio de nombres se llama **package** y permite organizar ahí las Interfaces y Clases que se agrupan por funcionalidad, clases relacionadas pertenecen a un mismo package, el cual que se parece a un árbol de directorio, tal como se organizan las carpetas en un sistema de archivos, de hecho los packages se almacenan en carpetas separadas.

En los mismos packages no pueden repetirse los mismos nombres de clases, ni dentro de una clase, los nombres de sus miembros, ni dentro de un bloque, los nombres de las variables.

```Java

package com.empresa.test;

```

### import

La palabra **import** permite trabajar con nombres de clases y de objetos *como si* estuvieran en el mismo package, evita que tengamos que escribir el nombre completo cada vez, y el programa queda así más legible, por ejemplo para a la clase Array, si al inicio del archivo se escribe ```import java.util.Array;``` ya no hará falta escribir ```java.util.Array``` cada vez que se usa, bastará poner ```Array```. Como desventaja, ya no se podrá usar ese nombre internamente, justamente el compilador lo verá como repetido; otro problema posible con import es cometer un error al escribir el import ya que es común que existan varios packages distintos con clases del mismo nombre.

```Java

import java.util.Array;

```


## Modificadores

### Modificadores de control de acceso

Permiten tener algún control sobre la visibilidad de una variable o función.

- Los *miembros* de clase, variables o métodos, aceptan estos modificadores:

**public**    : desde cualquier lado.  
**protected** : solo desde el mismo package (excepción: cuando es una sub-clase permite desde otros packages).  
***default***: solo desde el mismo package (sin excepción).  
**private**   : solo desde la misma clase.  

- Las clases solo pueden ser public o default(sin modificador).

En lo posible, se recomienda usar **private**, salvo en casos especiales.

### Otros modificadores 

#### final
Lo definido como final, no puede cambiar  

A una *clase* final, no se la puede extender.  
A un *método* final, no se lo puede sobreescribir desde una subclase.  
A una *variable primitiva* final, no se le puede cambiar el valor.  
A una *variable de referencia* final, no se le puede cambiar la referencia (siempre se referirá al mismo objeto, aunque ese objeto sí pueda cambiar sus valores internamente).  

#### static
*static* permite definir métodos o variables a nivel de clase, es decir, que son válidos para toda la clase, no para un objeto en particular sino para todos.

#### abstract
*abstract* permite declarar sin implementar, se pueden definir clases abstract que no permiten ser instanciadas, es decir no permiten la creación de objetos, salvo que se implementen desde otra clase,  los métodos abstract son solo firmas de métodos pero sin explicitar su contenido, también antes de usar deberán ser implementados por otras clases.

#### Concurrencia : synchronized y volatile
*synchronized* señala que ciertos objetos o métodos no pueden ser accedidos al mismo tiempo desde múltiples hilos de ejecución, en teoría esto posibilita un acceso concurrente a un recurso compartido, es decir que todos los participantes puedan ver un objeto coherente (como debería pasar por ejemplo con una cuenta bancaria), en la práctica esta sola palabra no alcanza y es un problema complejo de resolver.

*volatile* permite definir variables que al ser leídas desde un hilo de ejecución contienen el último valor escrito por cualquier otro hilo, evitando así todo tipo de caché, para dar coherencia entre lecturas-escrituras, desde ya que esto solo tampoco alcanzará esto para dar solución al problema de la concurrencia en la práctica.

