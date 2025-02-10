# Diseño del ATS del Futuro - LTI

## 1. Introducción
El **Applicant Tracking System (ATS)** es una herramienta clave en la optimización de los procesos de selección de talento en empresas de todos los tamaños. Estos sistemas permiten gestionar de manera eficiente la recepción, organización y evaluación de candidatos, facilitando la comunicación entre equipos de Recursos Humanos (RR.HH.), managers y candidatos.

LTI busca desarrollar un ATS del futuro, diferenciándose de la competencia mediante el uso avanzado de inteligencia artificial, automatización y herramientas colaborativas en tiempo real.

---

## 2. Definiciones Claves

### 2.1. Applicant Tracking System (ATS)
Un **ATS** es un software diseñado para ayudar a las empresas a gestionar su proceso de selección y contratación de talento. Sus funciones principales incluyen:
- Publicación de ofertas de trabajo en múltiples plataformas.
- Recepción y organización de candidaturas.
- Filtrado y evaluación de currículums.
- Programación y gestión de entrevistas.
- Comunicación con candidatos.

### 2.2. Ventajas Competitivas de un ATS
LTI se enfocará en desarrollar un ATS que proporcione ventajas competitivas clave:
- **Automatización avanzada** para reducir tareas manuales repetitivas.
- **Asistencia de IA** para mejorar la selección de candidatos y la comunicación.
- **Colaboración en tiempo real** entre reclutadores y managers.
- **Optimización del tiempo** en la contratación y toma de decisiones.
- **Experiencia del usuario mejorada**, tanto para RR.HH. como para los candidatos.

---

## 3. Problema a Resolver
El reclutamiento tradicional enfrenta diversos desafíos:
1. **Procesos lentos y burocráticos**: Las empresas invierten demasiado tiempo en revisar currículums y coordinar entrevistas manualmente.
2. **Falta de herramientas de colaboración**: La comunicación entre reclutadores, managers y candidatos es fragmentada.
3. **Poca eficiencia en la evaluación de candidatos**: La subjetividad y los sesgos afectan la toma de decisiones.
4. **Mala experiencia del candidato**: Los procesos largos y la falta de seguimiento pueden desmotivar a los postulantes.
5. **Dificultad en el seguimiento de métricas**: No todas las empresas pueden medir con precisión la efectividad de sus procesos de contratación.

LTI busca resolver estos problemas mediante una plataforma moderna que aproveche las últimas tecnologías para agilizar y mejorar el reclutamiento.

---

## 4. Funcionalidades Clave de LTI

### 4.1. Aumento de la Eficiencia para RR.HH.
- Publicación de ofertas de empleo automatizada.
- Gestión centralizada de candidaturas.
- Análisis y almacenamiento optimizado de currículums.

### 4.2. Colaboración en Tiempo Real
- Plataforma de comunicación integrada.
- Acceso compartido a perfiles de candidatos.
- Gestión de entrevistas colaborativa.

### 4.3. Implementación de Automatizaciones
- Filtrado automático de candidatos.
- Programación inteligente de entrevistas.
- Seguimiento automatizado del estado del candidato.

### 4.4. Asistencia de IA
- Análisis predictivo de candidatos.
- Chatbots para interacción con postulantes.
- Evaluación de sesgos en el proceso de selección.

---

## 5. Modelo de Negocio (Lean Canvas)
```plaintext
Problema:                         | Solución:
- Procesos lentos en RR.HH.       | - Automatización con IA
- Falta de colaboración           | - Plataforma en tiempo real
- Evaluación subjetiva            | - Análisis predictivo de candidatos

Propuesta de Valor:               | Métricas Clave:
- Optimización del reclutamiento  | - Tiempo de contratación
- Mejor experiencia del candidato | - Tasa de retención de talento

Canales:                          | Segmentos de Clientes:
- Empresas medianas y grandes     | - Departamentos de RR.HH.
- Plataformas de empleo           | - Agencias de reclutamiento

Estructura de Costos:             | Fuentes de Ingresos:
- Desarrollo y mantenimiento      | - Suscripción SaaS
- Infraestructura en la nube      | - Personalización empresarial
```

---

## 6. Casos de Uso

### Caso de Uso 1: Filtrado Automático de Candidatos
**Descripción:** El sistema analiza los currículums recibidos y los clasifica en función de los requisitos de la oferta.

**Diagrama:**
```plaintext
[Candidato envía CV] → [ATS analiza palabras clave] → [Candidato clasificado]
```

### Caso de Uso 2: Programación Inteligente de Entrevistas
**Descripción:** LTI coordina la disponibilidad de reclutadores y candidatos para agendar entrevistas de manera automática.

**Diagrama:**
```plaintext
[Reclutador selecciona candidatos] → [ATS consulta agendas] → [Fecha/hora confirmada]
```

### Caso de Uso 3: Evaluación de Sesgos en el Proceso de Selección
**Descripción:** La IA analiza patrones de contratación para detectar y corregir sesgos en la selección de talento.

**Diagrama:**
```plaintext
[Revisión de decisiones previas] → [Identificación de sesgos] → [Sugerencias de mejora]
```

---

## 7. Modelo de Datos
```plaintext
Entidad: Usuario
- ID (int, PK)
- Nombre (string)
- Correo (string, único)
- Rol (enum: reclutador, manager, candidato)

Entidad: OfertaLaboral
- ID (int, PK)
- Título (string)
- Descripción (text)
- Estado (enum: abierta, cerrada)

Entidad: Candidatura
- ID (int, PK)
- ID_Candidato (FK a Usuario)
- ID_Oferta (FK a OfertaLaboral)
- Estado (enum: en revisión, entrevista, contratado, rechazado)
```

---

## 8. Diseño del Sistema y Diagrama C4
Se mantiene una arquitectura basada en microservicios con integración de IA avanzada y automatización para maximizar la eficiencia y colaboración.

**Diagrama:**
```plaintext
[Frontend Angular] → [API Gateway] → [Servicios de Reclutamiento]
                                     → [Servicio de IA]
                                     → [Base de Datos PostgreSQL]
```

---

## 9. Conclusión
El ATS de LTI representa una solución moderna y efectiva para optimizar los procesos de reclutamiento, proporcionando herramientas avanzadas de IA y automatización. La implementación de funcionalidades como el filtrado automático de candidatos, la programación inteligente de entrevistas y la evaluación de sesgos mejora significativamente la eficiencia y equidad del proceso de selección.

Además, la capacidad de colaborar en tiempo real y gestionar información de manera centralizada permite a los equipos de RR.HH. tomar decisiones más rápidas y acertadas. Con un modelo de negocio basado en la escalabilidad y personalización, LTI está bien posicionado para revolucionar la industria del reclutamiento y generar un impacto positivo tanto en empresas como en candidatos.

La evolución del sistema continuará con mejoras basadas en el aprendizaje automático y el análisis predictivo, asegurando que el ATS de LTI siga siendo una herramienta innovadora y líder en su sector.

