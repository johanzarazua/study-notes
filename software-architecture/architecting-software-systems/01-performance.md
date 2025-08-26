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

- **Procesamiento ineficiente:** sucede cuando se cuenta con un algoritmo o proceso 
que no es eficuente, provocando que las peticiones se atrasen al pasar por el.
  
- **Acceso a recursos en serie:** sucede cuando se utiliza unicamente un hilo para 
la ejecucion de procesos, provocando bloque de acceso a recursos.

- **Capacidad limitada de recursos:** sucede cuando los recursos de hardware tiene alguna 
limitacion, provocando que solo se pueda atender un numero determinado de peticiones a al vez

El trabajo de un arquitecto de software es:
En un sistema existente, identificar en donde se estan generando colas de procesos y 
hacer modificaciones para mejorar el rendimiento.
Al diseñar o crear un nuevo sistema, identificar en que puntos puede producirse una cola
e intentar evitarlas para evitar problemas de rendimiento.

## Principios del rendimiento
Para mejorar el rendimiento de un sistema debemos contemplar los siguinetes principios.

### **Eficiencia.** 
La eficiencia suele medirse en un contexto de peticiones lineales, es decir, solo una 
entra al sistema y no puede entrar otra hasta que esta salga. La eficiencia se ve 
afectada por diferentes areas.

- **Uso de recursos:** contempla la eficiencia en uso de recuros IO (memoria, red, disco, etc.), 
asi como la eficiencia del CPU. El objetivo es que los recursos se usen de la mejor manera. 

- **Logica:** contempla la eficiencia en la logica de los algoritmos utilizados en la 
programacion y de los queries en base de datos. El objetivo es escribirlos de tal forma 
que hagan el minimo trabajo posible y utilicen una cantidad minima de CPU y IO 
(suele delegarse a los desarrolladores)

- **Almacenamiento de datos:** contempla el almcenamiento de datos en estructuras y 
bases de datos. El objetivo es que las consultas se ejecuten de manera eficiente, 
esto implica seleccionar las estruturas correctas e indexar datos en DB.

- **Cache:** su implementacion requiere cambios minimos en codigo y ofrece un gran 
beneficio en el tiempo de procesamiento

Si estas areas son manejadas de forma correcta, se asegurara que los tiempos de 
respuesta en un contexto de solicitudes lineales baje drasticamente.

### **Concurrencia**
La concurrencia consiste en el manejo de multiples peticiones al mismo tiempo, estas 
se ejecutan en paralelo pero cada una de ellas tiene un proceso independiente. Al 
manejar correctamente los puntos de la eficiencia nos aseguramos de que la ejecucion 
de cada proceso sea eficiente.

Para lograr la concurencia se necesita del hardware y el software, ya que ambos deben 
permitir el procesamiento de multiples peticiones. Del lado del software se deben 
considerar dos concpetos **colas** y **coherencia** esto debido a que al trabajar 
en un mismo hardware, las peticiones se pueden retrasar por bloqueos de recursos

### **Capacidad**
La capacidad esta relacionada con los recursos de hardware (CPU, memoria, disco, red, etc.), 
esto es algo que no suele tratarse o manejarse en el diseño de sistemas, por lo que se 
suele mantener un valor fijo haciendo que la eficiencia dependa unicamente de los 
puntos anteriores.

## Objetivos de rendimiento
Los objetivos de rendimiento en un sistema son dos:

- **Minimizar latencia**
- **Maximizar rendimeinto**

### Minimizar latencia
La latencia es el tiempo que transcurre entre la recepcion de una solicitud y el envio
de una respuesta. Esta medida suma el tiempo de espera y el tiempo de procesamiento, 
por lo que el objetivo es reducir estos dos tiempos.

### Maximizar rendimiento
El rendimiento es la tasa de solicitudes que un sistema puede manejar en un tiempo
determinado. Esta medida depende directamente de la **latencia** y la **capacidad**

>[!NOTE]
>El trabajo de un arquitecto de software es minimazar la latencia, ya que esto ayudara 
>a maximizar el rendimiento considerando que siempre tendremos la capacidad neceseria.

