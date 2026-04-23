## Definición de clases del sistema

### *Usuario*
+ idUsuario: Long
+ nombreCompleto: String

### Paciente (hereda de Usuario)
Posee **Expediente**
+ edad: Int
+ fechaNacimiento: Date
+ correoElectronico: String
+ numeroTelefonico: String

### Terapeuta (hereda de Usuario)
Atiende a **Paciente** y elabora **ReporteSesion**
+ visualizarLista()
+ seleccionarExpediente()
+ editarExpediente()

### Supervisor (hereda de Usuario)
Supervisa a **Terapeuta** y revisa a **ReporteSesion**
+ aceptarReporte()
+ rechazarReporte()
+ reenviarReporte()
+ agregarNotaCorrectiva()
+ seleccionarReporte()

### Administrador (hereda de Usuario)
Registra a **InformeConsentimiento** y a **EntrevistaSocioEconomica**
+ anexarEntrevista()
+ anexarConsentimiento()
+ anexarExpediente()

### *Documento*
+ idDocumento: Long
+ fecha: Date
---
+ almacenar()

### Expediente (hereda de Documento)
Asociado a: **Paciente**
Contiene: **ReporteSesion**, **InformeConsentimiento**, **EntrevistaSocioEconomica**
+ terapeutaAsociado: String
+ fechaProxCita: DateTime
+ idPaciente: Long

### ReporteSesion (hereda de Documento)
+ duracionSesion: Int
+ observacionesClinicas: String
+ estado:String
+ comentarios: String
+ idTerapeuta: Long

### InformeConsentimiento (hereda de Documento)
+ cuerpoDelTexto: String
+ acuerdoConfidencial: String

### EntrevistaSocioEconomica (hereda de Documento)
+ ingresoFamiliar: Decimal
+ alimentacion: Decimal
+ lugarProcedencia: String
+ vivienda: String
+ estadoSaludFamiliar: Int

## Diagrama de relación de clases

![Diagrama](/Documentación/Diagramas/DCDS.png)