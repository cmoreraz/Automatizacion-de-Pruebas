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