# Práctica 3_Desarrollo de servidor y Big Data

## Integrantes
- Mar Quispe
- Britney Cuichan

  
## Introducción
En esta práctica se migró la aplicación desarrollada en la práctica 2 hacia una arquitectura basada en MVC siguiendo la plantilla proporcionada.

El objetivo fue reorganizar la aplicación para mejorar la mantenibilidad, separación de responsabilidades y escalabilidad, manteniendo las mismas funcionalidades que antes.

## Diagrama MVC

![Diagrama MVC](https://github.com/BritneyG26/practica3_servidores/blob/main/arquitecturamvc.png)


## Explicación de componentes y responsabilidades
### Models
Ubicados en app/models/

Contienen:
- Lógica de dominio
- Conexión con SQLAlchemy
- Validación de contraseñas
- Campos del usuario

### View
Ubicadas en app/templates y app/static/

Contienen:
- login.html
- dashboard.html
- error.html
- base.html
- CSS y JS

### Controller 
Implementados en Blueprints en app/blueprints/

Están:
- auth/
- main/
- health/ 
- productos/
- usuarios/

## Evidencias de la separación lograda
Se puede observar la separación en la estructura del proyecto y en cómo se dsitribuyen las responsabilidades.

Los modelos Usuario y Producto gestionan la lógica de negocio y el acceso a datos.

Las vistas login.html y dashboard.html solo se encargan de mostrar infirmación sin ejecutar lógica de negocio ni consultas directas a la base de datos. 

Los controladores maneja las rutas, procesan las solicitudes y coordinan la interacción entre modelos y vistas.

Además, el uso de Marshmallow para validar datos y Swagger para documentar la API demuestra que la capa de presentación y la capa de datos están separadas.

## Reflexión sobre beneficios y desafíos del patrón MVC
# Beneficios
La migración al patrón MVC tiene varios beneficios. La mantenibilidad mejora ya que cada componente de la aplicación cumple una única responsabilidad, lo que facilita realizar cambios o extender fucnionalidades sin afectar otras partes del sistema. También se pueden agregar nuevas funcionalidades en los modelos, vistas y controladores de manera independiente. Además, las pruebas unitarias y de integración son mas sencillas ya que se pueden aplicar de forma independiente a cada capa de aplicación.

# Desafíos
Uno de los desafíos en migrar el código a esta arquitectura requiere reorganizar el proyecto. Además, en este caso al proporcionar la plantilla se tuvo que cambiar nombres como User por Usuario y username por nombre y fue necesario revisar todos los ficheros y test para que coincidieran. 


