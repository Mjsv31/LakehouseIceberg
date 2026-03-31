Data Lakehouse Laboratory (Iceberg + Spark)

Este proyecto es un laboratorio de datos local diseñado bajo la Medallion Architecture (Bronze, Silver, Gold), utilizando Apache Iceberg como formato de tabla y PySpark para el procesamiento.

Arquitectura Actual (v1.1.0)

Actualmente, el proyecto utiliza una arquitectura optimizada que conecta directamente a los metadatos:
  - Motor de Procesamiento: PySpark (Spark 3.5.5).
  - Formato de Tabla: Apache Iceberg.
  - Catálogo de Metadatos: JDBC Catalog directo a MariaDB (eliminando la dependencia de Hive Metastore).
  - Almacenamiento: MinIO (S3 Compatible) / Sistema de archivos local.
  - Consulta SQL: Trino (conectado al catálogo JDBC).

Historial de Versiones y Evolución

Este repositorio mantiene un registro de la evolución de la infraestructura:
  - v1.1 (Actual): Migración a JDBC Catalog. Se optimizó la infraestructura para conectar Spark y Trino directamente a MariaDB, reduciendo el consumo de recursos y simplificando el despliegue en Docker.
  - v1.0 (Legacy): Implementación inicial con soporte de Hive Metastore. Esta versión está disponible mediante el tag v1.0-hive-catalog para fines de comparación o compatibilidad.

Configuración del Entorno

Para replicar este laboratorio, asegúrate de contar con:
  - Docker & Docker Compose (puertos 3307 para MariaDB y 9000 para MinIO).
  - Driver JDBC: Descargar mariadb-java-client-3.5.7.jar y colocarlo en la carpeta /lib.
  - Variables de Entorno: Configurar las credenciales de S3 y JDBC
