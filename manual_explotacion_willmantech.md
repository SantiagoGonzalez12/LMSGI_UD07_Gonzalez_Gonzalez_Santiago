# Manual de Explotación Tecnológica en ERP/CRM WillmanTech S.L.
Este documento proporciona las directrices para la administración, mantenimiento y explotación del sistema de gestión de WillmanTech S.L., siguiendo los requisitos de calidad y usabilidad estándar internacional ISO/IEC/IEEE 26514:2022.

## Introducción y Arquitectura
El sistema ERP/CRM de WillmanTech S.L. está diseñado para centralizar los flujos de ventas y facturación de la organización.
* **Módulos  Activados**: El sistema tiene desplegados los módulos de _Ventas_, _CRM_, _Facturación_ y el motor de informes _QWeb_.
* **Topología Lógica**: La infraestructura se basa en una topología de microservicios por _Docker Compose_.
* **Componentes**: 
    * **Contenedor de Aplicación**: _Servidor Odoo_ para la lógica de negocio.
    * **Contenedor de BBDD**: _PostgreSQL_ para la persistencia de datos.
    * **Servicio de Renderizado**: Motor _wkhtmltopdf_ para la generación de documentos PDF.