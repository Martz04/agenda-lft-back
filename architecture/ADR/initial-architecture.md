# ADR: Arquitectura inicial

## Contexto
Realizar la aplicacion de agenda de cita, podriamos utilizar tecnologia de la nube pare hacer todo el desarrollo. Otra opcion podria ser montarlo en una maquina y red local utilizada por el hospital.

## Decision
Dado que multiples usuarios haran operaciones y para mantener bajo costo y manejabilidad de la infraestructura sin preocuparnos de parches y actualizaciones utilizaremos la tecnologia de la nube de AWS.

## Consequences
La aplicacion tendra que apegarse a los estandares de AWS y para mantener costos bajos se utilzaran las siguientes tecnologias:
* AWS Lambda (Python)
* DynamoDB
* SQS / SNS
* Cloudformation Template
* Route53
* API Gateway

La ventaja es que aprenderemos mas sobre estas tecnologias y tomaremos las ventajas de la misma infraestructura de AWS.

La desventaja es que Python tanto como AWS no tenemos tanta experiencia y podria demorar el tiempo de respuesta y desarrollo, asi como incrementar el tiempo de investigacion.
