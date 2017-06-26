
# OOP

## Objetos y Clases

La estructura del objeto se define mediante la **clase** a la que pertenece. Define lo que puede ser y hacer.

Los objetos de una clase tienen *estado* y *comportamiento*, es decir, lo que son y lo que hacen.

El **comportamiento** se define mediante **funciones** internas llamadas **métodos**

El **estado** se almacena en **campos**(fields) de uso interno y **propiedades** visibles a modificaciones externas.

Para evitar accesos indebidos se utiliza **encapsulamiento**. Mediante modificadores, que permiten regular la exposición de componentes, se define cuál es el contenido interno, volumen privado del objeto y la superficie visible, lo público. Ejemplo

```Java
class Cohete {
        public void lanzarCoheteSeguro() {
            if (verificarSistemasDeSeguridad()) {
                lanzarCohete();
            }          
        private lanzarCohete() {
            //...
        }
    }
}
```
El método lanzarCohete() **NO** debe ser accesible desde afuera del diseño de la clase, la seguridad DEBE chequearse *antes* del lanzamiento, por lo tanto ¿cómo evitar que sea accionado directamente sin el chequeo previo?, para que no ocurra ni siquiera por error sencillamente no debe ser posible hacerlo, para esto el lenguaje provee herramientas de control de scope/alcance, como las palabras public y private, entre otras, que si intentamos hacer el llamado directo darán un error de compilación.

El **polimorfismo** es lo que permite trabajar con objetos genéricos. Ejemplo:



# Tipos de datos de Referencia
Una diferencia con los tipos *primitivos* es que las asignaciones de referencias no copian al objeto entero, solo copian la *referencia*, al hacer **objA = objB**, luego **objB** refiere al mismo objeto que **objA**, no se crea un objeto nuevo, sino que representan al mismo; en cambio para los tipos *primitivos* las variables sí representan a los valores que contienen, y al hacer asignaciones se producen copias nuevas, **a = b** copia el *contenido* de **b** en **a**, son dos variables distintas y se pueden modificar independientemente.
El acceso a los objetos (a sus métodos y atributos, etc..) se hace mediante referencias, al crear un objeto de una determinada clase, es decir, una instancia de la clase, obtendremos una *referencia* al objeto y la podemos asignar a una variable, que será de tipo referencia obviamente. 


# Herencia, Interfaces

Una interfaz permite definir qué métodos son necesarios sin especificar el contenido concreto, por ejemplo si modelamos animales tendrán que implementarse diferentes formas del método caminar(), y distintas para cada uno, pero todos tendrán ese método, en ese caso se podría definir una interfaz general con una lista de métodos que sabemos tendrán que implementarse pero vacíos, sin código, luego en la clase específica que define a cada animal sí se implementa la funcionalidad, con la forma y manera particular según corresponda.

Ejemplo real de jerarquía de interfaces

![http://docs.oracle.com/javase/tutorial/figures/collections/colls-coreInterfaces.gif](http://docs.oracle.com/javase/tutorial/figures/collections/colls-coreInterfaces.gif)  
Imagen de http://docs.oracle.com



# Exceptions
