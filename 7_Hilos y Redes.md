## Procesos y Treads

Los programas pueden ejecutar varias tareas conjuntamente, mediante hilos y procesos, aún con sistemas que tienen un solo nucleo, dividiendo el tiempo de ejecución que le toca a acada una, más aún si el sistema posee varios procesadores o un procesador con muchos núcleos. 

Un proceso tiene acceso sólo a su propio espacio de memoria y a recursos de ejecución privados, en teoría es un entorno cerrado. Normalmente los programas se ejecutan como un proceso, pero un programa puede utilizar varios procesos que cooperan entre ellos o con procesos de otros sistemas comunicandosé por diferentes medios (ejemplo recursos de Inter Process Communication como pipes, o sockets)

Un thread o hilo es similara a un proceso pero con menos recursos, de hecho todo proceso tiene como mínimo un hilo de ejecución, el thread main, pero puede contener varios, la ventaja es que comparten el acceso a los recursos del proceso, por ejemplo el acceso a memoria y los archivos, sin embargo esto es también una desventaja porque requiere resolver el acceso al recurso compartido.


# Modelo Cliente-Servidor

# Sockets

# Formato JSON
