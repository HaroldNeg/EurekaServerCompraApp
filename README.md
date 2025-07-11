EurekaServerCompraApp
======================

Este repositorio contiene el microservicio `eureka-server` del sistema CompraApp.
Es el servidor de descubrimiento de servicios que permite a los microservicios encontrar y comunicarse entre sí sin necesidad de conocer direcciones fijas.

Descripción del Proyecto
-------------------------
Eureka Server forma parte del ecosistema Spring Cloud y proporciona un mecanismo de registro y descubrimiento dinámico de servicios.

En CompraApp, los microservicios como `productos-service`, `inventario-service`, y `gateway-server` se registran automáticamente en Eureka, permitiendo un enrutamiento dinámico.

Tecnologías utilizadas
-----------------------
- Java 21
- Spring Boot 3.5.3
- Spring Cloud Netflix Eureka Server 2025.0.0

Características
---------------
- Registro automático de microservicios clientes.
- Panel web de monitoreo del estado de instancias.
- Integración con Spring Cloud Config.
- Alta disponibilidad (con configuración adicional).

Ejecución del Proyecto
-----------------------
1. Clonar el repositorio:
   git clone https://github.com/HaroldNeg/EurekaServerCompraApp.git

2. Entrar al directorio del proyecto:
   cd EurekaServerCompraApp

3. Compilar el proyecto con Maven:
   mvn clean install

4. Ejecutar el microservicio:
   mvn spring-boot:run

Interfaz Web
------------
Por defecto, Eureka está disponible en:
http://localhost:8761

Desde ahí se puede visualizar el estado de los servicios registrados.

Configuración
-------------
El archivo `application.yml` debe contener:
- puerto del servidor
- configuración del nombre de aplicación
- deshabilitar registro automático (ya que este es el servidor)
- configuración del cliente Eureka (si se usa replicación entre múltiples instancias)

Ejemplo:
```yaml
eureka:
  client:
    registerWithEureka: false
    fetchRegistry: false

Licencia
-----------
Este proyecto está bajo una licencia de código abierto.

Contacto
-----------
Para soporte técnico o sugerencias, abre un issue en el repositorio.
