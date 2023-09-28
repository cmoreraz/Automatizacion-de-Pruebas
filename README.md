## Formato de Código
### Introducción
Este documento establecer una guia para formateo de código que se debe seguir en
todos los proyectos de automatización en nuestra organización. El formateo de
código consistente en mejorar la legibilidad y mantenibilidad del código, facilitando
la colaboración y reduciendo errores.
### Objetivos
+ Establecer una guía de estilo uniforme para el formateo de código.
+ Mejorar la legibilidad y comprensión del código.
+ Promover prácticas de programación limpias y consistentes.
+ Facilitar la revisión de código y la colaboración entre equipos.
### Convenciones Generales
+ Utiliza UTF-8 como codificación de caracteres.
+ Limita la longitud de línea a 80 caracteres para mejorar la legibilidad.
### Nombres de Variables y Funciones
+ Usa nombres descriptivos y significativos para variables y funciones.
+ Emplea el estilo camelCase para nombres de variables y funciones:
nombreVariable, calcularTotal.
+ Evita nombres de una sola letra, a menos que sea un contador de bucle.
### Comentarios
+ Utiliza comentarios para explicar fragmentos de código complejos o confusos.
+ Mantén los comentarios actualizados a medida que cambie el código.
+ Evita comentarios redundantes que simplemente repitan lo que hace el código.


### Estructura de Código
+ Utiliza líneas en blanco para separar bloques lógicos de código.
+ Agrupa las importaciones al inicio del archivo.
+ Divide el código en funciones y métodos coherentes y reutilizables.

#### Formateo de Expresiones
+ Agrega espacios alrededor de operadores: x = 5 + y.
+ Usa paréntesis para mejorar la claridad en las expresiones complejas.


### Formatea tu codigo
Para asegurarte de que el código siga este estándar, debemos utilizar
fmt-maven-plugin que consume la librería de estándar de Google, para ello debemos
agregar el siguiente plugin en el archivo pom.xml de nuestro proyecto.
```
<plugin>
<groupId>com.spotify.fmt</groupId>
<artifactId>fmt-maven-plugin</artifactId>
<version>2.20</version>
<configuration>
    <verbose>true</verbose>
    <style>google</style>
</configuration>
<executions>
    <execution>
    <phase>verify</phase>
    <goals>
        <goal>format</goal>
    </goals>
    </execution>
</executions>
</plugin>
```

Para formatear el código se debe usar el siguiente comando:
```sh
mvn com.spotify.fmt:fmt-maven-plugin:format
```