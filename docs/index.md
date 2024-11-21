# Práctica 3.1: Instalación de Tomcat y Maven para despliegue de aplicación Java

## Instalación de Tomcat

Para empezar, comenzaremos por instalar Tomcat.

![1](includes/images/2.png)

Y ahora creamos nuestro usuario administrador.

![2]( includes/images/3.png)

Después reiniciamos Tomcat y vemos si el servicio está activo.

![3]( includes/images/4.png)

![4]( includes/images/5.png)

## Despliegue manual mediante la GUI de administración

Una vez hecho esto entramos a la GUI.

![5]( includes/images/6.png)

Una vez dentro buscamos la sección que nos permite desplegar aplicaciones y cargamos un archivo de ejemplo.

![6]( includes/images/11.png)

Podemos ver que se desplegó correctamente.

![7]( includes/images/12.png)

y que podemos acceder a la aplicación.

![8]( includes/images/13.png)

## Despliegue con Maven

Instalamos Maven.

![9]( includes/images/7.png)

## Configuración de Maven

Añadimos ahora a tomcat un usuario para Maven.

![10]( includes/images/17.png)

Y configuramos Maven para que pueda desplegar en Tomcat.

![11]( includes/images/18.png)

Por último modificamos el POM del proyecto para que Maven pueda desplegarlo.

![12]( includes/images/24.png)

## Despliegue

Descargamos el proyecto de ejemplo.

![13]( includes/images/19.png)

y nos cambiamos a la rama del parche 1

![14]( includes/images/21.png)

Después compilamos el proyecto.

![15]( includes/images/25.png)

Podemos ver que efectivamente se ha creado el archivo WAR.

![16]( includes/images/27.png)

Y por último el proyecto funciona correctamente.

![17]( includes/images/26.png)

## Cuestiones

```Markdown
Habéis visto que los archivos de configuración que hemos tocado contienen contraseñas en texto plano, por lo que cualquiera con acceso a ellos obtendría las credenciales de nuestras herramientas.

En principio esto representa un gran riesgo de seguridad, ¿sabrías razonar o averigüar por qué esto está diseñado de esta forma?
```

En Tomcat, las contraseñas en texto plano (tomcat-users.xml) se usan por simplicidad en desarrollo, pero representan un gran riesgo si el archivo es accesible. Esto facilita la configuración rápida, pero expone credenciales sensibles. Para mitigar, usa cifrado, gestores de secretos y permisos estrictos. Evita estas prácticas en producción.
