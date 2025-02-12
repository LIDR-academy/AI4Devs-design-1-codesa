erDiagram
    USUARIOS {
        int usuario_id PK
        string nombre
        string email "UNIQUE"
        string rol
        date fecha_registro
    }

    CANDIDATOS {
        int candidato_id PK
        int usuario_id FK
        blob cv_documento
        string estado
    }

    EMPLEADOS {
        int empleado_id PK
        int usuario_id FK
        string departamento
        string cargo_actual
        int salario_actual
    }

    VACANTES {
        int vacante_id PK
        string titulo
        string departamento
        int salario_min
        int salario_max
        string estado
    }

    POSTULACIONES {
        int postulacion_id PK
        int candidato_id FK
        int vacante_id FK
        string estado_postulacion
        date fecha_postulacion
    }

    EVALUACIONES {
        int evaluacion_id PK
        int candidato_id FK
        int vacante_id FK
        int reclutador_id FK
        int puntaje_final
    }

    PROMOCIONES {
        int promocion_id PK
        int empleado_id FK
        int vacante_id FK
        string estado
    }

    ANALISIS_PREDICTIVO {
        int analisis_id PK
        int empleado_id FK
        int riesgo_fuga
        clob recomendaciones
    }

    %% Relaciones
    USUARIOS ||--o| CANDIDATOS : "puede ser"
    USUARIOS ||--o| EMPLEADOS : "puede ser"
    USUARIOS ||--o{ EVALUACIONES : "realiza"

    CANDIDATOS ||--o{ POSTULACIONES : "postula a"
    VACANTES ||--o{ POSTULACIONES : "recibe postulaciones de"

    EMPLEADOS ||--o{ PROMOCIONES : "es considerado para"
    VACANTES ||--o{ PROMOCIONES : "tiene promociones hacia"

    EMPLEADOS ||--|{ ANALISIS_PREDICTIVO : "tiene un análisis"