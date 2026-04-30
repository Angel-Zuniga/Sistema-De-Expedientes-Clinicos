# Arquitectura del sistema 

El sistema seguirá un estilo de **arquitectura en capas**, que organiza el sistema en niveles con responsabilidades definidas. Este enfoque nos permitirá separar la logíca de presentación, la lógica de negocio y el acceso a datos, facilitando la mantenibilidad y comprensión del sistema.

Para implementarlo, se adoptará un patrón **Controller-Service-Repository (CSR)**, que define una estructura concreta para cada una de las capas del sistema. En esta implementación la capa de presentación estará representada por controladores (Controller), la lógica de negocio estará centralizada en servicios (Service), y el acceso a datos será a través de repositorios (Repository).

# Justificación

La elección de la arquitectura y el patrón responde a las necesidades del sistema de gestión de expedientes clinicos, pues este requiere manejar reglas de negocio, restricciones de acceso y mecanismos de auditoría.

Comparado con un modelo MVC tradicional, la arquitectura que se usará ofrece una mejor separación de las responsabilidades. En MVC, la lógica de negocio suele recaer en el modelo o los controladores, generando un alto grado de acoplamiento. En cambio, el patrón CSR introduce una capa de servicios dedicada exclusivamente a la lógica de negocio, permitiendo centralizar validaciones, reglas clínicas y controles de acceso.

Por otro lado, consideramos que arquitecturas mas complejas como microservicios son innecesarias para el alcance actual del proyecto, porque introducirian una sobrecarga en la complejidad del mismo.

# Aplicación 

La arquitectura estará implementada en tres capas principales:
- Capa de presentación (Controller): Esta capa se encargará de gestionar las solicitudes del usuario, recibir entradas y devolver respuestas. La capa no contendrá logica de negocio, si no que delegara dichas operaciones a la capa de servicios. 
- Capa de lógica de negocio (Service): Esta capa concentrará las reglas del sistema, como las validaciones, el control de acceso basado en atributos (ABAC), restricciones sobre el estado del expediente, etc. También es responsable de generar los registros de auditoría tras evaluar cada operación sensible, conforme a lo definido en `Auditoria.md`.
- Capa de acceso a datos (Repository): Esta capa abstraerá la interacción con la base de datos, pues proporcionará métodos para consultar, almacenar y actualizar la información sin exponer detalles al resto del sistema. Incluye tanto los repositorios de datos de negocio como el repositorio de auditoría.

El flujo de operación del sistema está representando en el siguiente esquema:
```
Controller → Service → Repository → Base de datos
                 ↓
             Auditoría
```
En este flujo, cada solicitud es delegada por el Controller al Service, donde se evalúan las reglas de autorización ABAC y las reglas de negocio antes de interactuar con la base de datos. El Service también genera el registro de auditoría correspondiente (con resultado `PERMITIDO` o `DENEGADO`) que se persiste a través del Repository de auditoría, garantizando consistencia, seguridad y trazabilidad en cada operación.
