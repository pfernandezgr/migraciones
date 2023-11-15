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
