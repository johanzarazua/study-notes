# Rendimiento
El perfomance (rendimiento) es la velocidad de respuesta de un sistema bajo una 
carga de trabajo y un hardware determinado. La medida del rendimiento se ve afectado
por dos variables:

- **Carga de trabajo:** contempla el volumen de peticiones, la cantidad de datos
almacenados, etc.

- **Hardware:** contempla el tipo, la capacidad, etc.

Al momento de medir el rendimiento estas dos variables deben mantenerse fijas ya que 
modificarlas puede afectar la medicion. Esto no quiere decir que el sistema no podra 
soportar una carga de trabajo distinta o un hardware diferente.

El objetivo es mantener el rendimiento estable cuando la carga de trabajo aumente, 
puede tener degradaciones leves pero estas nunca deben pasar a se graves.
Asi como detectar problemas en el rendimiento a causa del hardware, los
cuales deben disminuir o desaparecer cuando se aumente la capacidad o se mejore el hardware

## Problemas de rendimiento
Un problema de rendimiento es el resultado de una cola de procesos acumulados, esto
termina provocando bloqueos en diferentes componentes como red, base de datos, cpu,
entre otros.

Los acumulamientos de proceso pueden deberse a multiples factores, pero es posible
agruparlos en 3 categorias:

- **Procesamiento ineficiente:** sucede cuando se cuenta con un algoritmo o proceso que no es eficuente, provocando que las peticiones se atrasen al pasar por el.
  
- **Acceso a recursos en serie:** sucede cuando se utiliza unicamente un hilo para la ejecucion de procesos, provocando bloque de acceso a recursos.

- **Capacidad limitada de recursos:** sucede cuando los recursos de hardware tiene alguna 
limitacion, provocando que solo se pueda atender un numero determinado de peticiones a al vez

El trabajo de un arquitecto de software es:
En un sistema existente, identificar en donde se estan generando colas de procesos y hacer modificaciones para mejorar el rendimiento.
Al diseñar o crear un nuevo sistema, identificar en que puntos puede producirse una cola
e intentar evitarlas para evitar problemas de rendimiento.

