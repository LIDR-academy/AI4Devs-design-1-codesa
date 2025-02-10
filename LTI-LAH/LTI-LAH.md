# Descripción del Software ATS LTI

## Valor Añadido y Ventajas Competitivas
El sistema ATS LTI es una plataforma avanzada de gestión de candidatos diseñada para mejorar la eficiencia y colaboración en tiempo real entre reclutadores y managers. Utiliza inteligencia artificial para optimizar procesos clave, como la clasificación de currículums, la coordinación de entrevistas y la evaluación de candidatos.

### Ventajas Competitivas:
- **Automatización Inteligente**: Uso de IA para filtrar y clasificar candidatos de manera eficiente.
- **Colaboración en Tiempo Real**: Permite que los reclutadores y managers trabajen conjuntamente en la evaluación de postulantes.
- **Interfaz Intuitiva**: Diseñada para facilitar la gestión de procesos de contratación de manera ágil y organizada.
- **Integración con Herramientas Externas**: Compatible con plataformas de RRHH y redes profesionales como LinkedIn.
- **Mejora en la Toma de Decisiones**: Proporciona análisis de datos y reportes detallados para optimizar las estrategias de contratación.

## Funciones Principales
1. **Recepción de CVs**: Permite la carga y recepción de currículums desde múltiples fuentes como portales de empleo y redes sociales.
2. **Filtrado y Clasificación de Candidatos**: Uso de algoritmos para priorizar postulantes en base a habilidades y experiencia.
3. **Gestión del Proceso de Selección**: Seguimiento del estado de cada candidato en cada etapa del proceso.
4. **Coordinación de Entrevistas**: Integración con calendarios y envío automatizado de invitaciones a entrevistas.
5. **Evaluación y Feedback**: Captura opiniones de los entrevistadores y facilita la toma de decisiones.
6. **Comunicación con Candidatos**: Notificaciones automáticas sobre el estado de su postulación.
7. **Análisis y Reportes**: Generación de informes sobre métricas clave del proceso de selección.

# Lean Canvas


```
<?xml version="1.0" encoding="UTF-8"?>
<mxfile>
  <diagram name="Lean Canvas ATS LTI">
    <mxGraphModel dx="661" dy="299" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="827" pageHeight="1169" math="0" shadow="0">
      <root>
        <mxCell id="0" />
        <mxCell id="1" parent="0" />
        
        <!-- Problem -->
        <mxCell id="2" value="Problem: Proceso de selección ineficiente, alta carga administrativa, falta de automatización y poca visibilidad en el pipeline de contratación." style="rounded=1;whiteSpace=wrap;html=1;" vertex="1" parent="1">
          <mxGeometry x="0" y="0" width="200" height="100" as="geometry" />
        </mxCell>
        
        <!-- Customer Segments -->
        <mxCell id="3" value="Customer Segments: Startups tecnológicas, empresas de formación, departamentos de RRHH." style="rounded=1;whiteSpace=wrap;html=1;" vertex="1" parent="1">
          <mxGeometry x="210" y="0" width="200" height="100" as="geometry" />
        </mxCell>
        
        <!-- Unique Value Proposition -->
        <mxCell id="4" value="Unique Value Proposition: ATS con IA para optimizar selección, reducir sesgo y mejorar eficiencia con colaboración en tiempo real." style="rounded=1;whiteSpace=wrap;html=1;" vertex="1" parent="1">
          <mxGeometry x="420" y="0" width="200" height="100" as="geometry" />
        </mxCell>
        
        <!-- Solution -->
        <mxCell id="5" value="Solution: Automatización de filtrado, integración con LinkedIn y portales de empleo, IA para recomendaciones y análisis de candidatos." style="rounded=1;whiteSpace=wrap;html=1;" vertex="1" parent="1">
          <mxGeometry x="0" y="120" width="200" height="100" as="geometry" />
        </mxCell>
        
        <!-- Channels -->
        <mxCell id="6" value="Channels: Página web, LinkedIn, marketing de contenido, partnerships con plataformas de empleo y formación." style="rounded=1;whiteSpace=wrap;html=1;" vertex="1" parent="1">
          <mxGeometry x="210" y="120" width="200" height="100" as="geometry" />
        </mxCell>
        
        <!-- Revenue Streams -->
        <mxCell id="7" value="Revenue Streams: Suscripción SaaS mensual, integración premium, consultoría para RRHH." style="rounded=1;whiteSpace=wrap;html=1;" vertex="1" parent="1">
          <mxGeometry x="420" y="120" width="200" height="100" as="geometry" />
        </mxCell>
        
        <!-- Cost Structure -->
        <mxCell id="8" value="Cost Structure: Desarrollo y mantenimiento, servidores, IA y procesamiento de datos, marketing y ventas." style="rounded=1;whiteSpace=wrap;html=1;" vertex="1" parent="1">
          <mxGeometry x="0" y="240" width="200" height="100" as="geometry" />
        </mxCell>
        
        <!-- Key Metrics -->
        <mxCell id="9" value="Key Metrics: % de reducción en tiempo de contratación, tasa de retención de clientes, número de CVs procesados mensualmente." style="rounded=1;whiteSpace=wrap;html=1;" vertex="1" parent="1">
          <mxGeometry x="210" y="240" width="200" height="100" as="geometry" />
        </mxCell>
        
        <!-- Unfair Advantage -->
        <mxCell id="10" value="Unfair Advantage: IA propietaria entrenada en el sector tech, enfoque en formación y desarrollo de ingenieros." style="rounded=1;whiteSpace=wrap;html=1;" vertex="1" parent="1">
          <mxGeometry x="420" y="240" width="200" height="100" as="geometry" />
        </mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>

```

# Diagrama de casos de uso


```
title "Casos de Uso - ATS LTI"

actor Recruiter
actor Manager
actor Candidate

usecase "Recepción y filtrado de CVs" as UC1
usecase "Gestión del proceso de selección" as UC2
usecase "Comunicación con candidatos" as UC3

Recruiter -> UC1 : Envía y revisa CVs
Manager -> UC2 : Administra selección
Candidate -> UC3 : Recibe notificaciones

note right of UC1
  - Recibe CVs de portales de empleo
  - Aplica filtros y palabras clave
  - Prioriza candidatos
end note

note right of UC2
  - Asigna estados a candidatos
  - Programa entrevistas
  - Comparte perfiles con el equipo
end note

note right of UC3
  - Notifica sobre avances
  - Coordina entrevistas
  - Responde preguntas frecuentes
end note

```

# Modelo entidad relacion 


```
title "Modelo Entidad-Relación - ATS LTI"

Entity(Candidate, "Candidate", "Información de los postulantes") {
    +id: UUID [PK]
    +first_name: String
    +last_name: String
    +email: String [UNIQUE]
    +phone: String
    +resume: Text
    +status: Enum(Pending, Reviewed, Interviewed, Hired, Rejected)
    +created_at: Timestamp
    +updated_at: Timestamp
}

Entity(Job, "Job", "Ofertas de empleo disponibles") {
    +id: UUID [PK]
    +title: String
    +description: Text
    +location: String
    +salary_range: String
    +status: Enum(Open, Closed)
    +created_at: Timestamp
    +updated_at: Timestamp
}

Entity(Application, "Application", "Relación entre candidatos y ofertas") {
    +id: UUID [PK]
    +candidate_id: UUID [FK -> Candidate.id]
    +job_id: UUID [FK -> Job.id]
    +applied_at: Timestamp
    +status: Enum(Submitted, Under Review, Interview Scheduled, Offered, Rejected)
}

Entity(Recruiter, "Recruiter", "Usuarios que gestionan las contrataciones") {
    +id: UUID [PK]
    +first_name: String
    +last_name: String
    +email: String [UNIQUE]
    +phone: String
    +created_at: Timestamp
    +updated_at: Timestamp
}

Entity(Interview, "Interview", "Entrevistas programadas para candidatos") {
    +id: UUID [PK]
    +application_id: UUID [FK -> Application.id]
    +recruiter_id: UUID [FK -> Recruiter.id]
    +date_time: Timestamp
    +status: Enum(Scheduled, Completed, Canceled)
    +feedback: Text
}

Entity(User, "User", "Usuarios con acceso al sistema") {
    +id: UUID [PK]
    +username: String [UNIQUE]
    +password: String
    +role: Enum(Admin, Recruiter, Manager)
    +created_at: Timestamp
}

Entity(Company, "Company", "Empresas que publican ofertas de trabajo") {
    +id: UUID [PK]
    +name: String
    +industry: String
    +location: String
    +website: String
    +created_at: Timestamp
    +updated_at: Timestamp
}

Relationship(Candidate, Application) {"1", "applies to", "N"}
Relationship(Job, Application) {"1", "has", "N"}
Relationship(Application, Interview) {"1", "is part of", "N"}
Relationship(Recruiter, Interview) {"1", "conducts", "N"}
Relationship(User, Recruiter) {"1", "is", "1"}
Relationship(Job, Company) {"N", "belongs to", "1"}
```

# Diagrama C4

```
title "Diagrama C4 - ATS LTI"

Person(Recruiter, "Recruiter", "Gestiona procesos de selección, revisa candidatos y coordina entrevistas")
Person(Manager, "Manager", "Supervisa y aprueba decisiones en el proceso de selección")
Person(Candidate, "Candidate", "Aplica a ofertas de trabajo y recibe actualizaciones del proceso")

System(ATS, "Applicant Tracking System", "Sistema para gestionar candidatos y procesos de selección de manera automatizada y eficiente")

Container(WebApp, "Web Application", "React", "Interfaz de usuario para gestión de candidatos, entrevistas y procesos de contratación")
Container(Backend, "Backend API", "Spring Boot", "Maneja la lógica de negocio, autenticación y persistencia de datos")
Container(Database, "Database", "PostgreSQL", "Almacena datos de candidatos, ofertas de trabajo y procesos de selección")

Recruiter -> WebApp : "Gestiona candidatos, revisa CVs y programa entrevistas"
Manager -> WebApp : "Aprueba decisiones y supervisa procesos"
Candidate -> WebApp : "Aplica a ofertas, recibe notificaciones y actualiza información personal"

WebApp -> Backend : "Solicita información y envía datos sobre candidatos y procesos"
Backend -> Database : "Guarda y recupera información de candidatos y procesos de selección"
```