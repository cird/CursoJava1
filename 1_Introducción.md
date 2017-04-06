# Introducción


 Ecosistema del lenguaje.
 
![http://docs.oracle.com/javase/tutorial/figures/getStarted/helloWorld.gif](http://docs.oracle.com/javase/tutorial/figures/getStarted/helloWorld.gif)
Image from http://docs.oracle.com


La estructura del objeto se define mediante la **clase** a la que pertenece.

Los objetos tienen estado y comportamiento.

El **estado** se almacena en **campos**(fields), estos son datos propios de la clase que usa internamente y **propiedades** que pueden modificarse externamente.

El **comportamiento** se define mediante **funciones** propias de la clase llamadas **métodos**

 
El **encapsulamiento** evita el acceso indebido. El volumen interno (privado)  y la superficie visible (público) , junto a otros modificadores, permiten regular la exposición de componentes internos. Ejemplo

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


Una interfaz permite definir qué métodos son necesarios pero sin especificar el contenido, por ejemplo si modelamos animales tendrán que implementarse diferentes formas del método caminar(), distintas para cada uno, pero todos tendrán ese método, en ese caso se podría definir una interfaz general con ese método, pero vacío, sin implementación, luego en la clase específica que define a cada animal se implementar la forma y manera particular según corresponda.

Un **espacio de nombres** es un contexto, donde los nombres de referencia son únicos, por ejemplo en el espacio de nombres de una ciudad suele tener nombres de calles que no se repiten, sin embargo, el mismo nombre de calle puede estar en otro pueblo, esto organiza las clases y las interfaces según la funcionalidad, en Java se llama **package**.
