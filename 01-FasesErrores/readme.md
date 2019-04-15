#### Sintaxis y Semantica de los Lenguajes de Programacion

* **Autor de la resolucion**   
  * **Usuario GitHub:** ginobarloco 
  * **Legajo:** 155.642-3
  * **Apellido:** Barloco
  * **Nombre:** Gino
  
 * **Numero y titulo del trabajo:** 01 - Fases de la Traduccion y Errores 
 
 * **Transcripcion del enunciado:** Identificar las fases de traducción y errores.

* **Hipotesis de trabajo:** Crear un programa en C y analizar las fases de traducción con sus posibles errores. A su vez, se corregira el programa en base al error que arroje la consola hasta obtener el resultado esperado.

 * **Tareas**
    * **Hello2.c**
        * **Comandos utilizados:** 
            * gcc -E hello2.c > hello2.i *--Verificamos las tareas realizadas por el preprocesador creando el archivo .i*
        * **Conclusión:** Al preprocesar el codigo fuente, se observa que se reemplazo el comentario "medio" por un espacio y la inclusión de la biblioteca estándar de entrada y salida.  
    * **Hello3.c**
        * **Comandos utilizados:**
            * gcc -E hello3.c > hello3.i 
            * gcc -S hello3.c *--Creamos el archivo ensamblador*
        * **Conclusión:** La semántica de la primera línea permite que no deba incluirse toda la biblioteca estándar de entrada-salida ya que al tratarse de un programa simple, solo utilizamos la funcion printf la cual se define previamente al main.
        Por otra parte, la diferencia que encuentro entre el **hello3.c** y el **hello3.i** es que este ultimo cuenta con 4 lineas adicionales en su codigo que inician con el simbolo #1.
   * **Hello4.c**
        * **Comandos utilizados:** 
            * gcc -E hello4.c > hello4.i
            * gcc -S hello4.c
            * as -o hello4.o hello4.s *--Creamos el archivo objeto*
            * gcc -o hello4 hello4.o *--Vinculamos el archivo objeto con la biblioteca estándar*
        * **Conclusión:** Al corregir el error que arrojaba la consola al generar el codigo en lenguaje Assembler en el hello3.c (Faltaba una llave para cerrar la funcion main), logramos crear el archivo **hello4.s** y se observan las instrucciones mencionadas en clase tales como *push, mov, call*, entre otras.  
        Al vincular el archivo **hello4.o** con la biblioteca estándar en la consola nos arroja el error de referencia a "prontf" con lo cual no puede crear el archivo ejecutable.
    * **Hello5.c**
        * **Comandos utilizados:** 
            * gcc -S hello5.c
            * as -o hello5.o hello5.s
            * gcc -o hello5 hello5.o
            * hello5.exe
        * **Conclusión:** Al ejecutar el archivo **hello5.exe**, observamos que la salida del proceso muestra el mensaje "*La respuesta es 4200640*" lo cual es incorrecta y se corrige en el siguiente archivo.
   * **Hello6.c**
        * **Comandos utilizados:** 
            * gcc -S hello6.c
            * as -o hello6.o hello6.s
            * gcc -o hello6 hello6.o
            * hello6.exe
        * **Conclusión:** Se puede observar que a la funcion "printf" le falta agregar la variable entera 'i' cuyo valor es 42 para que pueda mostrar correctamente el mensaje por pantalla. Al corregirlo, notamos que el mensaje es "*La respuesta es 42*" tal como lo pide el ejercicio.
   * **Hello7.c**
        * **Comandos utilizados:** 
            * gcc -o hello7 hello7.c
            * hello7.exe
        * **Conclusión:** El código funciona y muestra su resultado (a pesar de no incluir la biblioteca estándar) ya que el compilador se vincula a la biblioteca *stdio.h* por defecto.