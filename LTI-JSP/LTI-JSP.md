
SmartHire LTI : 

SmartHire ATS - Especificación del Sistema

Objetivo Principal:

Desarrollar un sistema de gestión de candidatos (ATS) que automatice y optimice el proceso completo de reclutamiento, desde la publicación de vacantes hasta la contratación final.

# Arquitectura del Sistema

## Componentes Principales

### 1. Módulo de Gestión de Vacantes
- Motor de publicación múltiple con APIs para integración con portales de empleo
- Sistema de plantillas para ofertas de trabajo
- Panel de control para gestión de publicaciones activas
- Métricas de efectividad por canal de publicación

### 2. Base de Datos de Candidatos
- Estructura escalable para almacenamiento de perfiles
- Sistema de indexación para búsqueda avanzada
- Gestión de documentos (CV, certificaciones, etc.)
- Control de versiones de documentos
- Sistema de etiquetado y categorización

### 3. Pipeline de Reclutamiento
- Motor de workflow configurable
- Sistema de estados y transiciones
- Reglas de automatización por etapa
- Triggers para acciones automáticas
- Dashboard de seguimiento en tiempo real

### 4. Sistema de Comunicaciones
- Motor de plantillas de correo
- Sistema de programación de comunicaciones
- Integración con servicios de correo
- Registro y trazabilidad de comunicaciones
- Capacidad de comunicación masiva

### 5. Módulo de Evaluación
- Motor de formularios dinámicos
- Sistema de puntuación configurable
- Comparador de candidatos
- Algoritmos de ranking automático
- Exportación de resultados

## Requisitos Técnicos

### Backend
- API RESTful con autenticación JWT
- Arquitectura microservicios
- Base de datos relacional para datos estructurados
- Base de datos NoSQL para documentos
- Cache distribuido
- Sistema de colas para procesos asíncronos

### Frontend
- SPA con React/Angular
- Diseño responsive
- Componentes reutilizables
- Sistema de temas
- Soporte offline
- PWA capabilities

### Seguridad
- Encriptación end-to-end
- RBAC (Role-Based Access Control)
- Auditoría de acciones
- Cumplimiento GDPR
- 2FA para accesos críticos

### Integraciones
- APIs para portales de empleo
- Conectores para redes profesionales
- Integración con sistemas de RRHH
- Webhooks para eventos
- SSO empresarial

## Métricas de Rendimiento
- Tiempo de respuesta < 200ms
- Disponibilidad 99.9%
- Soporte para 100,000 candidatos activos
- 1,000 usuarios concurrentes
- Procesamiento de 10,000 aplicaciones diarias

## Entregables Primera Fase
1. MVP con funcionalidades core
2. APIs documentadas
3. Panel de administración
4. Módulo de reportes básicos
5. Sistema de notificaciones

## Consideraciones de Escalabilidad
- Arquitectura cloud-native
- Containers y orquestación
- Auto-scaling
- Sharding de base de datos
- CDN para activos estáticos

Se adjunta diagrama Lean Canvan en la ruta ..\lean-canvas.mermaid

# Casos de Uso Core - Sistema de Gestión de Candidatos

# Casos de Uso Core - Sistema de Gestión de Candidatos

## CU-01: Gestión de Vacantes
**Actor Principal**: Reclutador
**Objetivo**: Crear y gestionar ofertas de trabajo
**Flujo Principal**:
1. Reclutador inicia sesión en el sistema
2. Sistema verifica credenciales y autentica al usuario
3. Reclutador crea nueva vacante
4. Sistema solicita información esencial:
   - Título del puesto
   - Descripción
   - Requisitos
   - Fecha límite
5. Reclutador completa la información
6. Sistema valida los datos
78. Sistema publica la vacante
6. Sistema genera URL única de postulación

**Flujos Alternativos**:
- Editar vacante existente
- Desactivar vacante
- Duplicar vacante

## CU-02: Postulación de Candidatos
**Actor Principal**: Candidato
**Objetivo**: Aplicar a una vacante
**Flujo Principal**:
1. Candidato accede a URL de vacante
2. Sistema muestra formulario de postulación
3. Candidato completa datos personales
4. Candidato adjunta CV
5. Sistema valida formato y tamaño de archivos
6. Sistema confirma postulación
7. Sistema notifica al reclutador

**Flujos Alternativos**:
- Guardar postulación parcial
- Aplicar a múltiples vacantes
- Actualizar información personal

## CU-03: Gestión de Pipeline
**Actor Principal**: Reclutador
**Objetivo**: Gestionar candidatos en proceso
**Flujo Principal**:
1. Reclutador inicia sesión en el sistema
2. Sistema verifica credenciales y autentica al usuario
3. Reclutador accede al pipeline
4. Sistema muestra candidatos por etapa:
   - Nuevos
   - En revisión
   - Entrevista
   - Evaluación
   - Seleccionado
5. Reclutador mueve candidatos entre etapas
6. Sistema registra cambios de estado
7. Sistema envía notificaciones automáticas

**Flujos Alternativos**:
- Filtrar candidatos
- Agregar notas
- Descartar candidatos

## CU-04: Evaluación de Candidatos
**Actor Principal**: Reclutador/Evaluador
**Objetivo**: Evaluar candidatos en proceso
**Flujo Principal**:
1. Reclutador/Evaluador inicia sesión en el sistema
2. Sistema verifica credenciales y autentica al usuario
3. Evaluador selecciona candidato
4. Sistema muestra perfil completo
5. Evaluador completa formulario de evaluación
6. Sistema calcula puntuación
7. Sistema actualiza ranking de candidatos

**Flujos Alternativos**:
- Solicitar información adicional
- Compartir evaluación
- Comparar candidatos

## CU-05: Comunicación con Candidatos
**Actor Principal**: Reclutador
**Objetivo**: Gestionar comunicaciones del proceso
**Flujo Principal**:
1. Reclutador inicia sesión en el sistema
2. Sistema verifica credenciales y autentica al usuario
3. Reclutador selecciona plantilla de comunicación
4. Sistema muestra preview personalizado
5. Reclutador ajusta mensaje
6. Sistema envía comunicación
7. Sistema registra en historial

**Flujos Alternativos**:
- Programar recordatorios
- Comunicación masiva
- Responder consultas

## Consideraciones Técnicas
- Autenticación y autorización por rol
- Validación de datos en tiempo real
- Registro de auditoría de acciones
- Gestión de archivos en la nube
- Notificaciones en tiempo real
- API REST para integraciones futuras

## Métricas de Éxito
1. Tiempo promedio de publicación < 5 minutos
2. Tasa de completitud de postulaciones > 80%
3. Tiempo de respuesta del sistema < 2 segundos
4. Satisfacción del usuario > 4/5

## Diseño del Sistema a Alto Nivel
Este sistema sigue una arquitectura de microservicios desacoplados, cada uno con su propia base de datos en Oracle, comunicación mediante API Gateway y autenticación con JWT (AWS Cognito).

1. API Gateway
Tecnología: AWS API Gateway
Función:
Punto de entrada único para solicitudes desde el frontend.
Distribuye las solicitudes a los microservicios.
Autenticación mediante JWT y AWS Cognito.
2. Servicio de Gestión de Usuarios
Tecnología: Spring Boot + Oracle (RDS)
Función:
Maneja la autenticación y autorización de usuarios.
Almacena información de reclutadores y administradores.
3. Servicio de Gestión de Candidatos
Tecnología: Spring Boot + Oracle (RDS)
Función:
Gestiona los perfiles de los candidatos.
Permite la actualización de información y carga de documentos.
4. Servicio de Gestión de Vacantes
Tecnología: Spring Boot + Oracle (RDS)
Función:
Maneja la creación, edición y publicación de vacantes.
Relaciona vacantes con reclutadores.
5. Servicio de Gestión de Postulaciones
Tecnología: Spring Boot + Oracle (RDS)
Función:
Administra las postulaciones de los candidatos.
Registra cambios en el estado de las postulaciones.
6. Servicio de Correos
Tecnología: Spring Boot + AWS SES + SQS
Función:
Envía notificaciones por correo a candidatos y reclutadores.
Usa Amazon SQS para colas de mensajes.
7. Frontend
Tecnología: Angular + AWS Amplify
Función:
Interfaz de usuario para reclutadores y candidatos.
Consume APIs de los microservicios.

Beneficios de esta Arquitectura
- Escalabilidad → Microservicios independientes con su propia BD en Oracle.
- Seguridad → Autenticación con JWT y AWS Cognito.
- Eficiencia → Spring Boot para un backend robusto y Angular para una UI moderna.
- Alta disponibilidad → Uso de AWS (RDS for Oracle, SQS, SES, Amplify).

## Enfoque del Diagrama C4
1- Descripción General
Este sistema sigue una arquitectura de microservicios en AWS, con los siguientes elementos clave:

Frontend en Angular (AWS Amplify)
Backend en Spring Boot, con microservicios independientes
Base de datos en Oracle (Amazon RDS)
Autenticación con AWS Cognito + JWT
Comunicación entre microservicios con REST API


Explicación del Diagrama
1. Contexto:

El usuario (reclutador o candidato) interactúa con la Web App (Angular).
La Web App envía solicitudes a través del API Gateway.
AWS Cognito maneja la autenticación y genera un JWT.
2. Contenedor:

API Gateway distribuye las peticiones a los microservicios de Spring Boot.
Cada microservicio tiene su propia base de datos Oracle en Amazon RDS.
El Servicio de Correos gestiona las notificaciones por email.
3. Componente (Servicio de Gestión de Vacantes):

Controller maneja las peticiones HTTP.
Service contiene la lógica de negocio.
Repository conecta con la base de datos Oracle.
JWT Authentication protege las rutas API.

Conclusión
- Arquitectura escalable con microservicios independientes.
- Bases de datos desacopladas para evitar dependencias.
- Autenticación segura con JWT.
- Estrategia de notificaciones con un servicio de correos.

## Descripción del Servicio de Gestión de Vacantes

El Servicio de Gestión de Vacantes es un microservicio independiente basado en Spring Boot que se encarga de:
- Crear, editar y eliminar vacantes.
- Publicar vacantes y generar enlaces de postulación.
- Relacionar vacantes con candidatos y reclutadores.
- Aplicar reglas de negocio para filtros y búsquedas avanzadas.
- Sincronizarse con otros microservicios como el de Usuarios y Postulaciones.

📌 Tecnologías Principales:

Spring Boot (Backend)
Spring Security + JWT (Autenticación)
Oracle Database (Persistencia)
Spring Data JPA (Acceso a datos)
REST API (Comunicación con otros servicios)
RabbitMQ (opcional) para eventos asíncronos

Explicación del Flujo
1. Un reclutador envía una solicitud al sistema (crear, editar o eliminar una vacante).
2. VacantesController recibe la solicitud y la valida con JWT.
3. VacantesService maneja la lógica de negocio, verificando:

Si el usuario tiene permisos.
Si la vacante cumple con los requisitos.
Si la vacante está dentro del plazo permitido.
4. VacantesRepository consulta la base de datos en Oracle para guardar o recuperar datos.
5. Si la vacante es publicada, se comunica con:
MS_Usuarios para obtener información del reclutador.
MS_Postulaciones para permitir aplicaciones.
MS_Correos para enviar notificaciones a candidatos interesados.
6. RabbitMQ puede enviar eventos de actualización a otros microservicios para mantener el sistema sincronizado.