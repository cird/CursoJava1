## Procesos y Treads

Los programas pueden ejecutar varias tareas conjuntamente, mediante hilos y procesos, si el sistema posee varios procesadores o varios núcleos, pero también con sistemas que tienen un solo nucleo, dividiendo el tiempo de ejecución que le toca a cada una.

Cada proceso tiene acceso sólo a su propio espacio de memoria y a recursos de ejecución privados, en teoría es un entorno cerrado. Normalmente los programas se ejecutan como un proceso, pero un solo programa puede utilizar varios procesos que cooperan entre ellos, procesos del mismo o de otros sistemas, comunicandosé por diferentes medios (ejemplos de recursos de IPC, Inter Process Communication son los pipes y los sockets)

Un thread o hilo es similara a un proceso pero con menos recursos asignados, de hecho todo proceso tiene como mínimo un hilo de ejecución, es el thread main, pero puede contener más, la ventaja de los threads es que comparten el acceso a los recursos del proceso, por ejemplo el acceso a memoria y los archivos, por lo tanto no necesitan comunicarse, sin embargo esto es también una desventaja porque aún así se requiere resolver el acceso al recurso compartido.

# Modelo Cliente-Servidor

# Sockets

# Formato JSON

Formato de texto para el intercambio de datos basado en lenguaje Javascript.

```Javascript
//ejemplo 1
{ "clave" : "valor" }

//ejemplo 2
{ "numeros" : [ 10, 20, 30, 40, 50] }

//ejemplo 3
{ "objeto" : {  "clave" : "valor",
                "numeros" : [ 10, 20, 30, 40, 50] }
}
```
