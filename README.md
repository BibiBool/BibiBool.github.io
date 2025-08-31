# BibiBool.github.io

## Architecure diagram

```mermaid
graph TD;
    subgraph Data Flow
        A[CloudFront S3 Logs] --> B(Airflow DAG);
        B --> C[Cleaned & Staged Data];
        C --> D[PostgreSQL Database];
    end

    subgraph Infrastructure
        E[Docker] --> F(Airflow: Webserver, Scheduler, Worker);
        F --> G(PostgreSQL: Database Service);
        G --> H(Metabase: Dashboard Service);
    end

    subgraph Data & Analytics
        D --> H;
    end

    classDef components fill:#f9f,stroke:#333,stroke-width:2px;
    class A,C,D components;

    linkStyle 0 stroke:#666,stroke-width:2px,color:red;
    linkStyle 1 stroke:#666,stroke-width:2px;
    linkStyle 2 stroke:#666,stroke-width:2px;
    linkStyle 3 stroke:#666,stroke-width:2px;
    linkStyle 4 stroke:#666,stroke-width:2px;
    linkStyle 5 stroke:#666,stroke-width:2px;

    style A fill:#FFC300,stroke:#333,stroke-width:2px;
    style B fill:#FF5733,stroke:#333,stroke-width:2px;
    style C fill:#DAF7A6,stroke:#333,stroke-width:2px;
    style D fill:#A9A9A9,stroke:#333,stroke-width:2px;
    style E fill:#428bca,stroke:#333,stroke-width:2px;
    style F fill:#9e8ad3,stroke:#333,stroke-width:2px;
    style G fill:#DAF7A6,stroke:#333,stroke-width:2px;
    style H fill:#E59866,stroke:#333,stroke-width:2px;
