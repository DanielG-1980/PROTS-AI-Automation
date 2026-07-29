# PROTS -- Pipeline Comercial IA

## Descripción

Proyecto desarrollado para la materia **Arquitectura de Flujos IA**.

Implementa un pipeline comercial automatizado utilizando **n8n**,
**OpenRouter**, **Airtable**, **Gmail** y **Slack**, incorporando un
proceso **Human-in-the-Loop** para la aprobación de prospectos antes del
contacto con el cliente.

------------------------------------------------------------------------

## Objetivos

-   Automatizar la recepción de prospectos.
-   Analizar solicitudes mediante un LLM.
-   Clasificar oportunidades comerciales.
-   Registrar información en Airtable.
-   Solicitar aprobación humana.
-   Contactar al prospecto únicamente cuando exista aprobación.
-   Mantener trazabilidad y gestión de errores.

------------------------------------------------------------------------

## Arquitectura

    Webhook
       │
    Validación
       │
    OpenRouter (LLM)
       │
    Procesamiento IA
       │
    Airtable
       │
    Gmail (Human-in-the-Loop)
       │
    ¿Aprobado?
     ├── Sí → Actualizar Airtable → Correo al Prospecto → Slack
     └── No → Actualizar Airtable → Slack

------------------------------------------------------------------------

## Tecnologías

-   n8n Cloud
-   OpenRouter
-   Airtable
-   Gmail
-   Slack
-   HTTP Webhooks
-   JavaScript

------------------------------------------------------------------------

## Base de Datos

Tablas implementadas:

-   Prospectos
-   Oportunidades
-   Clientes
-   Actividades
-   Productos

Campos destacados:

-   Empresa
-   Contacto
-   Email
-   Prioridad
-   Clasificación IA
-   Score IA
-   Resumen IA
-   Acción recomendada
-   Estado de aprobación
-   Fecha de aprobación

------------------------------------------------------------------------

## Human-in-the-Loop

El workflow utiliza el nodo **Gmail -- Send and Wait** para detener la
ejecución hasta que Gerencia apruebe o rechace el prospecto.

------------------------------------------------------------------------

## Gestión de errores

-   Validación de datos de entrada.
-   Rama dedicada para errores.
-   Notificaciones automáticas en Slack.
-   Registro del estado en Airtable.

------------------------------------------------------------------------

## Estructura del repositorio

    /
    ├── README.md
    ├── docs/
    │   ├── Memoria_Tecnica.pdf
    │   ├── Manual_Tecnico.pdf
    │   ├── Manual_Usuario.pdf
    │   └── Diagrama_Arquitectura.pdf
    ├── workflow/
    │   └── PROTS_Pipeline_Comercial_IA.json
    └── evidencias/
        ├── workflow.png
        ├── airtable.png
        ├── gmail.png
        └── slack.png

------------------------------------------------------------------------

## Autor

**Daniel Gilardi**

Proyecto académico -- Arquitectura de Flujos IA.
