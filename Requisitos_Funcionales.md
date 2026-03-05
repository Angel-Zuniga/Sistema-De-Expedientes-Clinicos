### RF - 01 Autenticación mediante código de un solo uso

**Requisito:** Inicio de sesión mediante código OTP.

**Descripción:**
El sistema deberá permitir que terapeutas y administradores inicien sesión mediante un código de un solo uso enviado al correo electrónico registrado en el sistema.

**Restricciones:**
- Solo usuarios previamente registrados pueden solicitar un código de acceso.
- El código debe enviarse al correo asociado al usuario.

**Criterios de aceptación:**
- El usuario puede solicitar un código de acceso desde la interfaz de inicio de sesión.
- El sistema envía un código al correo electrónico registrado.
- El usuario puede ingresar el código recibido para autenticarse en el sistema.

---

### RF - 02 Registro de pacientes

**Requisito:** Registro de pacientes.

**Descripción:**
El sistema deberá permitir registrar nuevos pacientes con la información necesaria para la creación de su expediente clínico.

**Restricciones:**
- Solo terapeutas o administradores pueden registrar pacientes.
- Los datos obligatorios del paciente deben ser proporcionados antes de guardar el registro.

**Criterios de aceptación:**
- El sistema permite registrar un paciente con datos válidos.
- El sistema guarda la información del paciente en la base de datos.
- El paciente aparece en los listados correspondientes.

---

### RF - 03 Consulta de pacientes

**Requisito:** Consulta de pacientes registrados.

**Descripción:**
El sistema deberá permitir consultar la información general de los pacientes registrados en el sistema.

**Restricciones:**
- La información mostrada dependerá del rol del usuario.

**Criterios de aceptación:**
- El sistema muestra la información del paciente solicitado.
- Los datos mostrados corresponden al paciente seleccionado.

---

### RF - 04 Edición de expediente clínico

**Requisito:** Edición de expediente clínico.

**Descripción:**
El sistema deberá permitir actualizar la información del expediente clínico de un paciente.

**Restricciones:**
- Solo usuarios autorizados pueden modificar un expediente.

**Criterios de aceptación:**
- El sistema permite modificar los datos del expediente clínico.
- Los cambios se guardan correctamente en la base de datos.

---

### RF - 05 Registro de sesiones psicológicas

**Requisito:** Registro de sesiones psicológicas.

**Descripción:**
El sistema deberá permitir registrar sesiones psicológicas asociadas a un paciente.

**Restricciones:**
- Cada sesión debe estar asociada a un paciente registrado.

**Criterios de aceptación:**
- El sistema permite registrar una sesión con la información correspondiente.
- La sesión queda asociada al expediente del paciente.

---

### RF - 06 Visualización operativa de expedientes

**Requisito:** Visualización operativa para administradores.

**Descripción:**
El sistema deberá permitir que los administradores consulten información operativa de los expedientes clínicos.

**Restricciones:**
- La información mostrada al administrador excluye contenido clínico.

**Criterios de aceptación:**
- El administrador puede visualizar datos operativos del expediente.
- El sistema no muestra información clínica sensible.

---

### RF - 07 Asignación de pacientes a terapeutas

**Requisito:** Asignación de pacientes.

**Descripción:**
El sistema deberá permitir asignar pacientes a terapeutas responsables de su atención.

**Restricciones:**
- Solo administradores pueden realizar asignaciones.

**Criterios de aceptación:**
- El sistema permite asignar un terapeuta a un paciente.
- El terapeuta asignado puede consultar el expediente del paciente.

---

### RF - 08 Navegación del sistema mediante menú

**Requisito:** Navegación mediante menú del sistema.

**Descripción:**
El sistema deberá proporcionar un menú de navegación para acceder a las diferentes funcionalidades disponibles.

**Restricciones:**
- Las opciones disponibles dependerán del rol del usuario autenticado.

**Criterios de aceptación:**
- El usuario puede navegar entre las funcionalidades del sistema.
- El menú muestra únicamente opciones disponibles para el rol del usuario.