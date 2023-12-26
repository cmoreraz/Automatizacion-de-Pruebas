## Empecemos

[Cucumber²](https://cucumber.io/docs/guides/) es una herramienta de pruebas que facilita escribir los requisitos de un sistema en inglés sencillo (o en más de 40 idiomas adicionales³) y luego automatizar esos requisitos convirtiéndolos en pruebas funcionales. Tener la capacidad de leer, comprender y colaborar durante la creación de las pruebas funcionales de un sistema tiene el potencial de generar cambios y mejoras profundos en la forma en que trabajamos y la calidad del software que entregamos.


Para comprender cuán profundo es este potencial, me gustaría comenzar describiendo los desafíos que existen en la forma en que normalmente probamos el software en el mundo actual. Parte de lo que describo en las siguientes secciones se toma desde un punto de vista ágil. Si no tiene la suerte de trabajar de esta manera, creo que debería ser fácil adaptar estas ideas a sus propias circunstancias para ver si se aplican.

### ¿Qué hay de malo en la forma en que probamos el software?
El mundo de las pruebas de software se encuentra en un estado de transición. La forma en que históricamente hemos
probado el software ha demostrado ser ineficiente e ineficaz. Es ineficiente porque muchas de las prácticas que seguimos
no escalan a medida que el software en el que estamos trabajando se vuelve más grande y complejo y también porque
hay una gran cantidad de desperdicio en nuestros procesos y flujos de trabajo debido al retrabajo causado por la
detección tardía de defectos. Es ineficaz porque, a pesar de nuestros mejores esfuerzos, los equipos de desarrollo de
software entregan regularmente software de baja calidad y que contiene muchos defectos.

Hace unos once años, un grupo de personas se reunió y creó el Manifiesto para el desarrollo de software ágil. Habían
pasado los años siguientes probando nuevas ideas sobre cómo los equipos pueden trabajar juntos para producir software
de mayor calidad de una manera más predecible. En los primeros días del movimiento Agile, gran parte de la escritura
se centraba en desarrolladores de software o en roles más centrados en la gestión. Se escribió muy poco sobre cómo
alguien que proviene de una experiencia en pruebas más tradicional debería participar en el proceso de desarrollo.

Dado que se escribió tan poco sobre el papel de los probadores de software, muchos equipos que trabajaban de forma
ágil asumieron que no había necesidad de un probador en el equipo. Otros trajeron a sus evaluadores pero les hicieron
continuar trabajando utilizando su enfoque tradicional para probar software. Ambos enfoques condujeron a muchos
problemas que discutiremos en este capítulo.

## Estructurando nuestro proyecto
Pendiente

## Formato de Código
### Introducción
Este documento establecer una guia para formateo de código que se debe seguir en
todos los proyectos de automatización en nuestra organización. El formateo de
código consistente en mejorar la legibilidad y mantenibilidad del código, facilitando
la colaboración y reduciendo errores.

### Problema
Cuando algo se repite una otra vez, es una señal de que tenemos una idea que no
acabamos de representar correctamente en el codigo, es por ello, que la duplicacion
es un gran problema ya que aumenta el tamaño del codigo y requirira una
modificacion bastante extensa cuando la logica de negocio cambia y no permite que
nuestras automatizaciones queden bien diseñadas, generando un esfuerzo
adicional, riesgos y una complegidad innecesaria.


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
Para asegurarte de que el código siga este estándar, podemos utilizar
fmt-maven-plugin, que consume la librería de estándar de Google y solo basta con adicionar el siguiente fragmento de codigo en la seccion de plugins que se encuentra en el archivo pom.xml de nuestro proyecto.
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