@startuml

' Definición de actores principales
actor "Reclutadores/RRHH" as RRHH
actor "Líderes de Equipo" as Lideres
actor "Candidatos Externos" as Candidatos
actor "Empleados Internos" as Empleados
actor "Sistema de IA" as IA

' Definición de actores secundarios
actor "Sistema CRM" as CRM
actor "Sistema HRIS" as HRIS
actor "Chatbot de IA" as Chatbot
actor "Sistema de Análisis Predictivo" as Analisis

' Módulo: Reclutamiento Inteligente (ATS)
rectangle "Reclutamiento Inteligente (ATS)" {
  usecase "Filtrado Automático de CVs" as Filtrado
  usecase "Evaluación Predictiva de Candidatos" as Evaluacion
  usecase "Automatización de Entrevistas" as Entrevistas
}

RRHH --> Filtrado
IA --> Filtrado
IA --> Evaluacion
RRHH --> Evaluacion
Candidatos --> Entrevistas
IA --> Entrevistas
Chatbot --> Entrevistas

' Módulo: Gestión de Talento Interno y Desarrollo
rectangle "Gestión de Talento Interno y Desarrollo" {
  usecase "Identificación de Empleados para Promoción" as Promocion
  usecase "Recomendación de Planes de Desarrollo" as Desarrollo
}

IA --> Promocion
HRIS --> Promocion
Empleados --> Desarrollo
IA --> Desarrollo
Lideres --> Desarrollo

' Módulo: Prevención de Fuga de Talento
rectangle "Prevención de Fuga de Talento" {
  usecase "Detección de Riesgo de Fuga" as Fuga
  usecase "Sugerencia de Estrategias de Retención" as Retencion
  usecase "Análisis de Desempeño y Satisfacción" as Desempeno
}

Analisis --> Fuga
IA --> Fuga
IA --> Retencion
RRHH --> Retencion
IA --> Desempeno
HRIS --> Desempeno

' Módulo: CRM y Engagement
rectangle "CRM y Engagement" {
  usecase "Seguimiento de Candidatos" as Seguimiento
  usecase "Comunicación Automatizada con Candidatos" as Comunicacion
  usecase "Manejo de Relación con Talento Interno" as RelacionInterna
}

CRM --> Seguimiento
IA --> Seguimiento
Candidatos --> Comunicacion
Chatbot --> Comunicacion
IA --> RelacionInterna
Empleados --> RelacionInterna

' Módulo: Análisis Predictivo y Reportes
rectangle "Análisis Predictivo y Reportes" {
  usecase "Análisis de Eficiencia en Contrataciones" as AnalisisContratacion
  usecase "Predicción de Necesidades de Talento" as PrediccionTalento
  usecase "Optimización de Estrategias de Retención" as OptimizacionRetencion
}

IA --> AnalisisContratacion
IA --> PrediccionTalento
RRHH --> AnalisisContratacion
Lideres --> PrediccionTalento
IA --> OptimizacionRetencion
Analisis --> OptimizacionRetencion

' Relaciones include y extend
Fuga ..> Desempeno : <<include>>
Retencion ..> OptimizacionRetencion : <<include>>
Promocion ..> Desarrollo : <<extend>>

@enduml
