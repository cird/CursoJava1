## Variables y Alcance

Un **espacio de nombres** es un contexto donde los nombres son únicos, por ejemplo en una carpeta no puede haber archivos con el mismo nombre, pero sí pueden estar en carpetas diferentes; en Java el espacio de nombres se llama **package** y permite organizar ahí las Interfaces y Clases, generalmente agrupadas por funcionalidad.

#### Variables 
  - **de instancia**, pertenecen a objetos  
  - **de clase**, valen para toda la clase, se declaran como ***static***  
  - **locales**, son de uso interno de una función o bloque.  
  - **parámetros**, son las usadas en los argumentos de una función.  

## Modificadores

### Modificadores de control de acceso

Los modificadores de acceso permiten tener algún control sobre la visibilidad de una variable o función.
Los miembros de clase, variables o métodos, pueden aceptar estos modificadores:

**public**    : desde cualquier lado
**protected** : solo desde el mismo package (excepción: cuando es una sub-clase permite desde otros packages)
***default***: solo desde el mismo package (sin excepción)
**private**   : solo desde la misma clase.

Las clases solo pueden ser public o default(sin modificador).

En lo posible, usar private, salvo en casos especiales.

### Otros modificadores 

**final**
Lo definido como final no puede cambiar:

A una *clase* final, no se la puede extender.
A un *método* final, no se lo puede sobreescribir desde una subclase
A una *variable primitiva* final, no se le puede cambiar el valor
A una *variable de referencia* final, no se le puede cambiar su referencia (siempre refiere al mismo, aunque este sí pueda variar internamente).

**static**
static define métodos o variables a nivel de clase (es decir, válidos para toda la clase)

**abstract**

**synchronized**

**volatile**


## Estructuras de datos.

#### Arreglo

El arreglo/array es un objeto contenedor básico para un conjunto ordenado de valores fijos de un mismo tipo. La cantidad de elementos del arreglo es fija y se establece al momento que se crea. Los **arrays** en Java no son tipos primitivos sino de referencia, por lo tanto no pueden copiarse mediante asignación, tienen además la propiedad **length** que contiene la cantidad de elementos del array.


```Java
int[] arreglo = new int[10];

System.out.println(" Tamaño array : " + arreglo.length);
```

![https://docs.oracle.com/javase/tutorial/figures/java/objects-tenElementArray.gif](https://docs.oracle.com/javase/tutorial/figures/java/objects-tenElementArray.gif)

fuente: https://docs.oracle.com

#### Lista


#### Pila/Stack


#### Cola/Queue


#### Diccionario/Map 



