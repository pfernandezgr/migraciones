# README: Proyecto APIA

## Documentación Técnica

### Procedimiento para Desarrollar en APIA

#### Gestión de Repositorio Compartido

Es esencial contar con un repositorio que permita la gestión del código desarrollado por todos los programadores involucrados en el proyecto.

#### Configuración del Ambiente Local

**Software Necesario:**
- IDE: Eclipse
- Java: 1.8
- pgAdmin [Descargar aquí](http://www.pgadmin.org)

**Configuración de Eclipse:**
- Servidor: Tomcat 9
- Config Path: /Server/CARPETA_CONFIG_SERVER
- Lunch Configuration:
  - Arguments:
    - Program Arguments: start
  - VM Arguments:
    ```
    -Dcatalina.base="C:\Development\eclipse-workspace1\.metadata\.plugins\org.eclipse.wst.server.core\tmp1"
    -Dcatalina.home="C:\Development\apache-tomcat\apache-tomcat-9.0.55"
    -Dwtp.deploy="C:\Development\eclipse-workspace1\.metadata\.plugins\org.eclipse.wst.server.core\tmp1\wtpwebapps"
    -Djava.endorsed.dirs="C:\Development\apache-tomcat\apache-tomcat-9.0.55\endorsed"
    ```
  - Web Modules:
    - Document Base: URL_del_proyecto\target\ApiaTramites
    - Path: /Apia
    - Auto-reloading enabled: false

**Configuración del Proyecto:**
Después de configurar el servidor, procedemos a la configuración del proyecto. Asegúrese de haber descargado el proyecto desde GitLab.

### Procedimiento para Descargar el Repositorio de GitLab

1. Abrir el proyecto (File -> Open Project from File System).
2. En Eclipse, abrir el archivo `config.properties` ubicado en la carpeta `properties`. Si no cuenta con esta carpeta, debe reutilizar (clonar, copiar/pegar) la carpeta `properties_example`.
3. Dentro de este archivo, configure el path a la base de datos, el usuario y la contraseña (encriptada en Base64). Ejemplo:

    ```
	Db.url=jdbc:postgresql://192.168.9.58:5432/NombreDeBaseDeDatos
	Db.usr=nombreUsuario
	Db.pwd=contraseñaEnBase64
	Db.insusr= nombreUsuario
	Db.inspwd= contraseñaEnBase64
    ```
4. Asegúrese de que exista una conexión entre el host donde se encuentra el servidor Tomcat (en este caso, localhost si se está trabajando desde el PC con Eclipse) y el servidor que aloja la base de datos.

### Configuración de Maven

Para descargar la última versión de Apia, utilizaremos Maven. A continuación, una breve descripción de Maven:

Maven es una herramienta de gestión de proyectos ampliamente utilizada en el desarrollo de software, especialmente en proyectos basados en Java. Su objetivo principal es facilitar la construcción, el empaquetado, compilación y la gestión de dependencias de un proyecto.

Estas son algunas de las funciones principales de Maven:

- **Gestión de dependencias:** Maven facilita la gestión de las dependencias de un proyecto. Puede declarar las dependencias del proyecto en un archivo de configuración llamado "pom.xml" (Project Object Model), y Maven se encarga de descargar automáticamente las dependencias requeridas desde repositorios remotos.

- **Construcción y gestión del ciclo de vida:** Maven proporciona un conjunto de fases y metas predefinidas que definen el ciclo de vida de un proyecto. Estas fases incluyen la compilación, prueba, empaquetado, instalación y despliegue del proyecto. Al ejecutar un objetivo específico, Maven realiza las tareas necesarias en el orden correcto según el ciclo de vida del proyecto.

- **Construcción consistente:** Maven promueve una estructura de proyecto estandarizada y una forma consistente de organizar los recursos y el código fuente. Esto facilita la comprensión y el mantenimiento del proyecto, especialmente cuando varios desarrolladores trabajan en él.

- **Gestión de configuraciones y perfiles:** Maven permite definir diferentes perfiles de construcción que se pueden activar según las necesidades. Esto es útil cuando se deben realizar compilaciones para diferentes entornos (desarrollo, prueba, producción) o cuando se requiere configuraciones específicas para diferentes plataformas.

- **Generación de informes y documentación:** Maven puede generar informes automáticos sobre diferentes aspectos del proyecto, como cobertura de pruebas, métricas de código, documentación del proyecto, entre otros. Esto ayuda a mantener un control sobre la calidad del código y facilita la generación de documentación actualizada del proyecto.

**Configuración:**
Para que Maven pueda descargar las librerías necesarias y luego se compile el proyecto, necesitamos la siguiente configuración:


img
img
img

### Configuración Adicional

5. Iniciamos el Tomcat en la solapa de servidores de Eclipse.
- Modo Debug permite hacer cambios en las clases de Java y el servidor hará un auto reload del proyecto.
- Modo Start inicia el servidor con las clases compiladas al momento del inicio de este. No permitirá recargar el proyecto si hacemos cambios en las clases Java.

6. URL para ingresar a la aplicación web: [localhost:PORT/Apia](localhost:PORT/Apia)


### Servidor de Base de Datos

APIA utiliza una base de datos PostgreSQL que se deberá configurar en un servidor al que todos los programadores involucrados puedan acceder desde su equipo local (PC con Eclipse y servidor Tomcat).




Este README proporciona una guía completa para configurar el entorno de desarrollo, descargar el proyecto desde GitLab y utilizar Maven para gestionar las dependencias y compilar el proyecto APIA. Siga cuidadosamente cada paso para garantizar una configuración correcta y un desarrollo sin problemas.
