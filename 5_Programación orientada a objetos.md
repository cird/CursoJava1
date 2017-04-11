
# OOP

## Objetos y Clases

La estructura del objeto se define mediante la **clase** a la que pertenece.

Los objetos tienen *estado* y *comportamiento*.

El **estado** se almacena en **campos**(fields), estos son datos propios de la clase que usa internamente y **propiedades** que pueden modificarse externamente.

El **comportamiento** se define mediante **funciones** propias de la clase llamadas **métodos**
 
El **encapsulamiento** evita accesos indebidos. El volumen interno (privado)  y la superficie visible (público) , junto a otros modificadores, permiten regular la exposición de componentes internos. Ejemplo

```Java
class Cohete{
public void lanzarCoheteSeguro(){
           if( verificarSistemasDeSeguridad() ){           
              lanzarCohete();
           }  
          
private lanzarCohete(){
          //...
}
}}
```
El método lanzarCohete() **NO** debe ser accesible desde afuera del diseño de la clase,  la seguridad antes del lanzamiento, si no se debe permitir ni siquiera por error que sea accionado sin chequear la seguridad, entonces sencillamente no debe ser posible hacerlo, para eso el lenguaje da herramientas de control de alcance, como las palabras public y private, entre otras. 

El **polimorfismo** permite trabajar con objetos genéricos. Ejemplo:

# Tipos de datos de Referencia
El acceso a los objetos (y a sus métodos y atributos, etc..) se hace mediante referencias, por ejemplo, al crear un objeto de una determinada clase, lo que se llama una instancia de la clase, obtendremos una *referencia* al objeto y la podemos asignar a una variable, que será de tipo referencia obviamente. 
Una diferencia con los tipos *primitivos* es que las asignaciones de referencias no copian al objeto entero, solo copian la *referencia*, al hacer **objA = objB**, luego **objB** refiere al mismo objeto que **objA**, no se crea un objeto nuevo, sino que representan al mismo; en cambio para los tipos *primitivos* las variables sí representan a los valores que contienen, y al hacer asignaciones sí se producen copias nuevas, **a = b** copia el *contenido* de **b** en **a**, en el caso primitivo son dos variables distintas y se pueden modificar independientemente.

# Herencia, Interfaces

Una interfaz permite definir qué métodos son necesarios sin especificar el contenido concreto, por ejemplo si modelamos animales tendrán que implementarse diferentes formas del método caminar(), y distintas para cada uno, pero todos tendrán ese método, en ese caso se podría definir una interfaz general con una lista de métodos que sabemos tendrán que implementarse pero vacíos, sin código, luego en la clase específica que define a cada animal sí se implementa la funcionalidad, con la forma y manera particular según corresponda.

Ejemplo real de jerarquía de interfaces

![http://docs.oracle.com/javase/tutorial/figures/collections/colls-coreInterfaces.gif](http://docs.oracle.com/javase/tutorial/figures/collections/colls-coreInterfaces.gif)  
Imagen de http://docs.oracle.com



# Exceptions
