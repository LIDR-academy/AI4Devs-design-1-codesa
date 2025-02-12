### **1. Descripción del software LTI**

**Descripción breve del software LTI:**
El sistema LTI (Learning Tools Interoperability) tiene como objetivo integrar diversas herramientas de aprendizaje (tanto internas como externas) con plataformas educativas de manera sencilla y estandarizada. A través de LTI, las plataformas de gestión de aprendizaje (LMS) pueden conectarse con aplicaciones externas sin la necesidad de realizar integraciones personalizadas. Esto proporciona una experiencia más fluida para los usuarios y permite a los administradores gestionar de forma eficiente la infraestructura educativa.

**Valor añadido:**
- **Interoperabilidad estandarizada**: LTI permite que diferentes sistemas educativos se comuniquen entre sí de manera eficiente.
- **Escalabilidad**: Capacidad de agregar nuevas herramientas sin alterar el sistema principal.
- **Reducción de costos**: Eliminación de integraciones personalizadas, lo que reduce el tiempo y costo de desarrollo.
  
**Ventajas competitivas:**
- Compatibilidad con múltiples plataformas de aprendizaje.
- Facilidad de integración y configuración.
- Rápida adopción en instituciones educativas de todos los tamaños.

**Funciones principales:**
1. **Autenticación**: El sistema LTI permite la autenticación del usuario desde la plataforma LMS sin necesidad de nuevos inicios de sesión.
2. **Acceso a herramientas externas**: Proporciona acceso a herramientas externas como sistemas de gestión de exámenes, herramientas de colaboración y contenido educativo.
3. **Sincronización de datos**: Sincroniza los datos del usuario, progreso y resultados con la plataforma principal (LMS).
4. **Gestión de seguridad**: Provee mecanismos de seguridad robustos para garantizar que solo usuarios autorizados accedan a las herramientas externas.

### **2. Lean Canvas**

El Lean Canvas es un modelo de negocio que ayuda a visualizar los componentes clave del proyecto. A continuación te presento los elementos más importantes para el software LTI:

| **Elemento**              | **Descripción**                                                     |
|---------------------------|---------------------------------------------------------------------|
| **Problema**               | Las plataformas educativas tienen dificultades para integrar herramientas externas de forma eficiente. |
| **Segmento de clientes**   | Instituciones educativas, administradores de LMS, y desarrolladores de herramientas educativas. |
| **Propuesta de valor**     | Simplificación de la integración de herramientas externas en plataformas educativas. |
| **Canales**                | Contacto directo con universidades, conferencias educativas, marketing digital. |
| **Flujo de ingresos**      | Licencias del software, suscripción mensual por cada plataforma LMS integrada. |
| **Estructura de costos**   | Desarrollo y mantenimiento del software, soporte al cliente. |
| **Métricas clave**         | Número de plataformas LMS que usan LTI, tiempo de integración. |
| **Ventaja competitiva**    | Estándar en el mercado educativo, apoyo para múltiples herramientas educativas. |

### **3. Casos de uso**

#### **Caso de uso 1: Autenticación de usuario**
- **Descripción**: Un usuario ingresa a un LMS (Learning Management System), se autentica y accede a una herramienta externa integrada mediante LTI sin tener que iniciar sesión de nuevo.
- **Actores**: Estudiante, Plataforma LMS, Proveedor de herramienta externa (como un sistema de evaluación).
- **Diagrama de caso de uso:**

```plaintext
  +------------------+       +-----------------------+       +---------------------------+
  |    Estudiante    |------>|  Plataforma LMS       |------>|   Herramienta Externa     |
  +------------------+       +-----------------------+       +---------------------------+
            |                     |
            | Autenticación        | Autenticación LTI
            |-------------------->|-------------------->
            |                     |
```

#### **Caso de uso 2: Acceso a contenido interactivo**
- **Descripción**: El estudiante accede a una herramienta externa de aprendizaje (por ejemplo, un video interactivo) a través del LMS, utilizando la interoperabilidad LTI.
- **Actores**: Estudiante, Plataforma LMS, Herramienta externa (video interactivo).
- **Diagrama de caso de uso:**

```plaintext
  +------------------+       +-----------------------+       +---------------------------+
  |    Estudiante    |------>|  Plataforma LMS       |------>|   Herramienta Interactiva  |
  +------------------+       +-----------------------+       +---------------------------+
            |                     |
            | Solicitar acceso     | Cargar contenido interactivo
            |-------------------->|-------------------->
            |                     |
```

#### **Caso de uso 3: Sincronización de resultados**
- **Descripción**: Después de realizar una evaluación en una herramienta externa, los resultados obtenidos se sincronizan con el LMS para que el profesor pueda acceder a ellos.
- **Actores**: Estudiante, Plataforma LMS, Herramienta externa (evaluación).
- **Diagrama de caso de uso:**

```plaintext
  +------------------+       +-----------------------+       +---------------------------+
  |    Estudiante    |------>|  Plataforma LMS       |<------|   Herramienta Evaluación  |
  +------------------+       +-----------------------+       +---------------------------+
            |                     |
            | Enviar resultados    | Sincronización de datos
            |-------------------->|-------------------->
            |                     |
```

### **4. Modelo de Datos**

**Entidades y atributos:**

1. **Usuario**:
   - `id_usuario` (Integer)
   - `nombre` (String)
   - `email` (String)
   - `rol` (String: 'estudiante', 'profesor', 'administrador')

2. **PlataformaLMS**:
   - `id_lms` (Integer)
   - `nombre` (String)
   - `url` (String)
   - `tipo` (String)

3. **HerramientaExterna**:
   - `id_herramienta` (Integer)
   - `nombre` (String)
   - `tipo` (String)
   - `url` (String)

4. **ResultadoEvaluacion**:
   - `id_resultado` (Integer)
   - `id_usuario` (Integer, FK)
   - `id_herramienta` (Integer, FK)
   - `resultado` (Decimal)
   - `fecha` (Datetime)

**Relaciones:**
- Un **Usuario** puede tener varios **ResultadosEvaluacion**.
- Un **LMS** puede tener varias **HerramientasExternas** integradas.
- Una **HerramientaExterna** puede generar varios **ResultadosEvaluacion** para diferentes **Usuarios**.

### **5. Diseño del sistema a alto nivel**

El sistema se diseñará con una arquitectura modular en la que el **LMS** se integra con múltiples **HerramientasExternas** a través del estándar LTI. La comunicación entre las entidades se realizará de forma segura utilizando el protocolo LTI.

**Diagrama de alto nivel:**
```plaintext
   +-----------------+
   |  Plataforma LMS |
   +-----------------+
         |
  Integración LTI
         |
   +----------------------+
   | Herramientas Externas |
   +----------------------+
```

### **6. Diagrama C4**

Aquí te muestro un diagrama C4 a nivel de componente para ilustrar la **comunicación entre el LMS y una herramienta externa**:

```plaintext
  +----------------------------------------------------+
  |             Plataforma LMS                        |
  |   +--------------------------+                   |
  |   |   Módulo de Autenticación |                   |
  |   +--------------------------+                   |
  |   |   Módulo de Integración  |                   |
  |   +--------------------------+                   |
  +----------------------------------------------------+
               |                         |
  LTI API      |                         |
               v                         v
      +----------------+        +---------------------+
      | Herramienta    |        | API LTI             |
      | Externa        |        |                     |
      +----------------+        +---------------------+
```

El **Módulo de Autenticación** asegura que el usuario sea autenticado correctamente en la plataforma LMS antes de acceder a las herramientas externas. El **Módulo de Integración** maneja las solicitudes LTI y facilita la comunicación con las herramientas externas.

Este es un diseño de alto nivel, pero puedes profundizar más en la implementación según sea necesario.