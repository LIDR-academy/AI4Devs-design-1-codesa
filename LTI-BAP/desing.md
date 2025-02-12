graph TD;
    
    subgraph "Frontend"
        Web[Web App (React/Next.js)]
        Mobile[Mobile App (Flutter)]
    end

    subgraph "API Gateway"
        Gateway[API Gateway (Kong / Apigee)]
    end

    subgraph "Backend Microservices"
        Auth[🔐 Auth Service]
        ATS[📝 ATS Service]
        CRM[📞 CRM Service]
        HRIS[🏢 HRIS Service]
        IA[🤖 AI Engine]
        Analytics[📊 Analytics Service]
        Notification[📨 Notification Service]
    end

    subgraph "Databases & Storage"
        PostgreSQL[(PostgreSQL - Relational DB)]
        MongoDB[(MongoDB - NoSQL)]
        Redis[(Redis - Cache)]
        S3[Data Lake (AWS S3)]
    end

    subgraph "AI & ML Services"
        MLModel[🤖 ML Model (Talent Prediction)]
        Chatbot[💬 AI Chatbot]
        FugaTalent[📉 Fuga de Talento Predictor]
        Desarrollo[📈 Desarrollo Profesional Recommender]
    end

    subgraph "External Integrations"
        CRMExt[(CRM: HubSpot/Salesforce)]
        HRISExt[(HRIS: Workday/SAP)]
    end

    Web -->|REST API / GraphQL| Gateway
    Mobile -->|REST API / GraphQL| Gateway
    Gateway -->|Routes Requests| Auth
    Gateway -->|Routes Requests| ATS
    Gateway -->|Routes Requests| CRM
    Gateway -->|Routes Requests| HRIS
    Gateway -->|Routes Requests| IA
    Gateway -->|Routes Requests| Analytics
    Gateway -->|Routes Requests| Notification

    ATS -->|Data Storage| PostgreSQL
    CRM -->|Data Storage| MongoDB
    HRIS -->|Data Storage| PostgreSQL
    IA -->|Data Processing| MLModel
    MLModel -->|Stores Results| S3

    Analytics -->|Reads Data| PostgreSQL
    Analytics -->|Reads Data| MongoDB
    Analytics -->|Reads Data| Redis
    Analytics -->|Stores Processed Data| S3

    IA -->|Uses Model| FugaTalent
    IA -->|Uses Model| Desarrollo
    Chatbot -->|Interacts with Users| Web
    Chatbot -->|Interacts with Users| Mobile

    CRM -->|Syncs Data| CRMExt
    HRIS -->|Syncs Data| HRISExt

    Notification -->|Sends Notifications| Web
    Notification -->|Sends Notifications| Mobile
    Notification -->|Sends Emails| Email[📧 Email Service]
