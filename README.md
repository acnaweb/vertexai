# Vertex AI


## Pre-built Container

```sh
docker run -it us-docker.pkg.dev/vertex-ai/training/sklearn-cpu.1-0:latest sh
```

### With Machine Learning Service to use 

```mermaid  
flowchart TD
    %% Definições de estilos para tema light
    classDef startEnd fill:#f0f8ff,stroke:#005f99,stroke-width:2px,color:#005f99,font-weight:bold;
    classDef decision fill:#fffacd,stroke:#ffa500,stroke-width:2px,color:#333,font-weight:bold;
    classDef action fill:#e6ffe6,stroke:#008000,stroke-width:2px,color:#004d00;

    training_data{"Have training data?"}:::decision
    training_data -->|yes| ML_API["ML API"]:::action
    training_data -->|no| write_training_code{"Can you write training code?"}:::decision
    write_training_code -->|no| auto_ml["Auto ML"]:::action
    write_training_code -->|yes| write_model_sql{"Write model training in SQL?"}:::decision    
    write_model_sql -->|yes| bigquery_ml["Big Query ML"]:::action
    write_model_sql -->|no| custom_model["Custom Model"]:::action
```

## References

- https://cloud.google.com/vertex-ai?hl=en
- https://cloud.google.com/vertex-ai/docs/predictions/pre-built-containers
- https://cloud.google.com/vertex-ai/docs/training/pre-built-containers
- https://cloud.google.com/vertex-ai/docs/start/training-methods