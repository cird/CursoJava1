
## if - else
Se utiliza para expresar decisiones. La expresión dentro del if se evalúa, si el resultado es verdadero se ejecuta sentencia_1, si es falso se ejecuta sentencia_2. En ningún caso se ejecutan ambas.

´´´Java
        if(expresión) 
          sentencia_1;
        else 
          sentencia_2;
´´´

La cláusula else es opcional. sentencia_1 y sentencia_2 pueden ser una sentencia simples o bloques. 

Para el caso de bloques queda

´´´Java
        if(expresión) {
          secuencia de sentencias_1;
        }else{
          secuencia de sentencias_2;
        }
´´´
        
Si bien se *pueden* "anidar" if's, es decir se pueden poner a la vez otros if-else dentro de alguno de los bloques if-else, no se aconsejan anidar demasiados if's, vuelven el código menos legible.

## switch

Esta sentencia compara una variable con una lista de constantes, cuando encuentra una correspondencia ejecuta la sentencia o el bloque de sentencias asignado a esa constante.

´´´Java
switch (variable) {
  case constante_1:
        secuencia de sentencias;
        break;
  case constante_2:
         secuencia de sentencias;
         break;
  case constante_3:
         secuencia de sentencias;
         break;
  ...
  default:
         secuencia de sentencias;
         break;
}
´´´

Cuando se encuentra una coincidencia, se ejecutan las sentencias asociadas hasta encontrar la sentencia **break**, en ausencia de **break** el programa sigue adelante hasta encontrar un break o la llave de cierre del switch, por ende, podríamos estar ejecutando más de un case por error. La sentencia default se ejecuta si no se encuentra ninguna correspondencia luego de evaluar todos los **case**. Con **switch** solo se puede comprobar la igualdad, no se pueden evaluar expresiones relacionales o lógicas. Dentro de un switch no puede haber dos constantes con los mismos valores. **switch** también permite anidar otras sentencias switch, pero tampoco es recomendable.

## Bucles

### for, while, do-while, break, continue

### for

Se utiliza para repetir un bloque de código una cantidad de veces determinada.

´´´Java
for(inicializacion ; condicion ; incremento/decremento) {
    sentencia1;
    sentencia2;
    sentenciaN;
}
´´´
Agrupa 3 acciones 

*Inicialización*, Asigna valor inicial a la variable de control del bucle.
*Condición*, Determina cuando finaliza el bucle, evalúa la expresión antes de cada iteración, si el resultado es falso, finaliza. 
*Incremento/decremento*, se ejecuta al final de cada iteración para modificar la variable de control en cada iteración.

### while
Permite repetir la ejecución de un bloque de código, mientras una determinada condición sea cierta, se usa sobretodo cuando la cantidad de iteraciones no se conoce en el momento de programar sino que se define en runtime, es decir, mientras corre el programa.

´´´Java
while(expresion) {
    sentencia1;
    sentencia2;
sentenciaN;
}
´´´

### do-while
El bucle do-while examina la condición al final del mismo. Entonces un bucle do-while se ejecute al menos una vez. ( en cambio while y for que comprueban la condición antes de ingresar al bucle)

´´´Java
do {
    sentencia1;
    sentencia2;
    sentenciaN
} while (expresion);
´´´



