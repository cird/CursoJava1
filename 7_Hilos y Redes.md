## Procesos y Threads

Mediante hilos y procesos los programas pueden ejecutar varias tareas conjuntamente, si el sistema posee varios procesadores o varios núcleos puede hacerlas en paralelo, al mismo tiempo, pero con sistemas que tienen un solo nucleo también pueden ejecutarse múltiples tareas dividiendo el tiempo de ejecución que le toca a cada una.

Cada proceso tiene acceso sólo a su propio espacio de memoria y a recursos de ejecución privados, idealmente es un entorno cerrado. Los programas se ejecutan normalmente como un único proceso, pero también pueden utilizar varios procesos que cooperan entre ellos, sean del mismo sistema o de otros sistemas mediante alguna comunicación interproceso IPC ( Inter Process Communication, por ejemplo: pipes y sockets)

Un thread(o hilo) es similar a un proceso pero tiene menos recursos asignados, todo proceso corre como mínimo un hilo de ejecución, que es el thread main, pero puede contener más; una ventaja de usar threads es que utilizan los recursos que ya posee el proceso, por tanto se pueden crear de una manera más ágil, ya que comparten el acceso a los recursos del proceso, por ejemplo el acceso a memoria y los archivos, se puede acceder a éstos sin necesidad de comunicación, aún así esto no elimina el problema del acceso al recurso compartido, ni los problemas de sincronización y concurrencia, sea con hilos o con procesos, deberán ser resueltos.

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
{
  "objeto": {
    "clave": "valor",
    "numeros": [10, 20, 30, 40, 50]
  }
}
```
