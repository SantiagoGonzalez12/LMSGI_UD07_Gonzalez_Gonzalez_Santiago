# Manual de Explotación Tecnológica en ERP/CRM WillmanTech S.L.
Este documento proporciona las directrices para la administración, mantenimiento y explotación del sistema de gestión de WillmanTech S.L., siguiendo los requisitos de calidad y usabilidad estándar internacional ISO/IEC/IEEE 26514:2022.

## 1. Introducción y Arquitectura
El sistema ERP/CRM de WillmanTech S.L. está diseñado para centralizar los flujos de ventas y facturación de la organización.
* **Módulos  Activados**: El sistema tiene desplegados los módulos de _Ventas_, _CRM_, _Facturación_ y el motor de informes _QWeb_.
* **Topología Lógica**: La infraestructura se basa en una topología de microservicios por _Docker Compose_.
* **Componentes**: 
    * **Contenedor de Aplicación**: _Servidor Odoo_ para la lógica de negocio.
    * **Contenedor de BBDD**: _PostgreSQL_ para la persistencia de datos.
    * **Servicio de Renderizado**: Motor _wkhtmltopdf_ para la generación de documentos PDF.


## 2. Guía de Instalación y Reinstalación
Para garantizar que el sistema esté disponible en entornos productivos, se debe seguir el procedimiento de despliegue automatizado.  

### Requisitos Previos
* Docker y Docker Compose instalados en el host. 
* Acceso al repositorio de configuración *LMSGI_UD07*.

### Pasos de Despliegue
* **Configuración de Entorno**: Definir las variables de entorno en el archivo .env (credenciales de DB, puertos y claves maestras). 
* **Levantamiento del Entorno**: Ejecutar el comando _docker-compose up -d_ para inicializar los contenedores en segundo plano. 
* **Dependencias del SGBD**: El sistema requiere un volumen persistente para _PostgreSQL_ para evitar la pérdida de datos entre reinicios.


## 3. Seguridad y Control de Acceso
La integridad y confidencialidad de la información se gestiona mediante una política de acceso basado en roles (RBAC). 
* **Roles**:
    * **Administrador**: Acceso total a la configuración del sistema, copias de seguridad y gestión de usuarios. 
    * **Contable**: Permisos de creación y validación de facturas, exportación de datos (JSON/UBL) y gestión de impuestos. 
    * **Comercial**: Acceso limitado a la gestión de leads en el CRM y creación de pedidos de venta. 
* **Políticas de Seguridad**: Se exige el uso de contraseñas complejas y la rotación periódica de las mismas para todos los perfiles.  
