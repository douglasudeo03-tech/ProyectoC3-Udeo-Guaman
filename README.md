# Resumen del sistema de Gestion de bibliotecas 
## Descripcion del caso

Este sistema permitirá registrar cada libro que ingresa, verificar su disponibilidad en segundos, gestionar los préstamos y devoluciones, enviar recordatorios automáticos a los usuarios morosos y mantener un historial claro de todas las actividades. Además, busca mejorar la experiencia tanto de los bibliotecarios como de los lectores, haciendo que encontrar un libro sea tan rápido como buscarlo en el catálogo digital.


## Objetivos del sistema

Los objetivos del sistema se enfocan en cumplir el factor principan que es facilitar la gestion en los libros u otras cosas. Para lograrlo, se establecen dos grupos de objetivos:

 Los objetivos del sistema: 
  
  * Lo que el sistema **"Debe hacer"** (RF):
     Corresponden a las acciones concretas que el usuario —sea bibliotecario o lector— podrá realizar dentro del sistema.
  * Las **"caracteristicas"** que debe cumplir (RNF):
     Describen las cualidades y condiciones que el sistema debe tener para asegurar una experiencia estable, rápida y confiable.


## Requerimientos

### Requerimientos funcionales:
* **RF1 Registro de Libros:**  El Sistema debe permitir al Bibliotecario registrar nuevos títulos en el catálogo (incluyendo título, autor, ISBN y cantidad de ejemplares).
* **RF2 Registro de Préstamo:** El Sistema debe permitir al Bibliotecario registrar el préstamo de un ejemplar a un usuario específico, asignando una fecha de devolución.
* **RF3 Registro de Devolución:** El Sistema debe permitir registrar la devolución de un libro, actualizando la disponibilidad del ejemplar en el catálogo.
* **RF4 Búsqueda de Catálogo:**  El Sistema debe permitir a los usuarios o al Bibliotecario buscar libros por Título, Autor o ISBN.
* **RF5 Alerta de Vencimiento:**  El Sistema debe generar una lista o alerta de los préstamos cuya fecha de devolución está vencida o por vencer.


### Requerimientos no funcionales:
* **RNF1 Seguridad de Acceso:**  Solo el personal de la biblioteca (Bibliotecario/Administrador) debe poder acceder a las funciones de registro, préstamo y devolución mediante un inicio de sesión
* **RNF2 Integridad de Datos: ** El Sistema debe asegurar que un libro no se pueda prestar si la cantidad de ejemplares disponibles es cero.
* **RNF3 Rendimiento de Búsqueda:**  La búsqueda en el catálogo (RF4) debe devolver resultados para una base de datos de hasta 5,000 libros en menos de 3 segundos.



## Casos de prueba

* **CP01**

 * Tipo: Unitario
 * Requerimiento: RF2, RNF2
 * Datos: Intento de Préstamo del libro "El Quijote", con 0 ejemplares disponibles.
 * Resutado esperado: El sistema debe mostrar un mensaje de error ("Ejemplares no disponibles") y denegar el préstamo.
 * Resultado obtenido: Éxito.


* **CP3**

 * Tipo: Unitario
 * Requerimiento: RNF1
 * Datos: Intento de iniciar sesión con el nombre de usuario LectorA" y contraseña "pass123" para la función de Préstamo
 * Resutado esperado: El sistema debe mostrar un mensaje de error ("Acceso Denegado") y denegar la entrada a las funciones transaccionales.
 * Resultado obtenido: Éxito.


* **CP4**

 * Tipo: Validacion
 * Requerimiento: RNF3
 * Datos: Un usuario realiza una búsqueda por el título "Historia". Se mide el tiempo de respuesta. 
 * Resutado esperado: El proceso de búsqueda y visualización de resultados en la pantalla debe completarse en un tiempo máximo de 3 segundos.
 * Resultado obtenido: Las credenciales fueron aceptadas y se ingresó al sistema sin inconvenientes


* **CP5**

 * Tipo: Validacion
 * Requerimiento: RF5
 * Datos: Se genera la lista de Alerta. Préstamo #123 tiene fecha de devolución: Ayer.
 * Resutado esperado: El reporte generado debe incluir el Préstamo #123 en la lista de vencidos.
 * Resultado obtenido: Éxito



## Tipos de propuesta de mantenimiento 

* **Problema:** El sistema presenta fallos ocasionales al momento de actualizar el estado de los préstamos
 
 
  * **Tipo de Mantenimiento:** Mantenimiento correctivo
  * **Accion:** Revisar y reparar el módulo encargado de gestionar los cambios de estado de los libros. Esto incluye corregir errores en la base de datos, ajustar los procesos de actualización y garantizar que los registros se sincronicen correctamente en tiempo real.
  * **Justificacion:** Es necesario solucionar estos fallos para evitar inconsistencias en la disponibilidad de los libros y mejorar la confiabilidad del sistema. Un catálogo preciso permite que los usuarios encuentren información real y evita conflictos en los procesos de préstamo y devolución.


* **Problema:** El módulo de búsqueda de libros se vuelve lento cuando el catálogo supera cierta cantidad de registros, haciendo que los usuarios tengan que esperar demasiado para obtener resultados y dificultando la localización rápida de materiales.
  

 
  * **Tipo de Mantenimiento:** Mantenimiento Perfectivo
  * **Accion:** Optimizar el algoritmo de búsqueda y mejorar la indexación de datos en la base de datos. Esto puede incluir aplicar filtros más eficientes, reestructurar consultas y mejorar la organización interna del catálogo para acelerar el procesamiento.
  * **Justificacion:** Aunque el sistema funciona, mejorar su rendimiento permitirá ofrecer una experiencia más fluida y rápida. Una búsqueda ágil facilita el trabajo del personal bibliotecario y mejora la satisfacción de los usuarios al encontrar información sin demoras.


## Reflexion sobre el control de versiones 

El control de versiones es fundamental para asegurar que el Sistema de Gestión de Bibliotecas evolucione de forma ordenada y segura. Gracias a esta herramienta, es posible llevar un registro detallado de cada cambio realizado en el código: desde la corrección de errores en el módulo de préstamos hasta la incorporación de nuevas funciones como reservas en línea o reportes automáticos.
Esto permite identificar con precisión cuándo se introdujo un problema, restaurar una versión estable en caso de fallos y comprender mejor la trayectoria de desarrollo del sistema.
