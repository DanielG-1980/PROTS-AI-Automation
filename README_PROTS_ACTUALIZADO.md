# PROTS – Pipeline Comercial IA

## Descripción
Proyecto desarrollado para la materia **Arquitectura de Flujos IA**.

Implementa un pipeline comercial automatizado utilizando **n8n**, **OpenRouter**, **Airtable**, **Gmail** y **Slack**, incorporando un proceso **Human-in-the-Loop** para la aprobación de prospectos antes del contacto con el cliente.

---

## Objetivos

- Automatizar la recepción de prospectos.
- Analizar solicitudes mediante IA (LLM).
- Clasificar oportunidades comerciales.
- Registrar información en Airtable.
- Solicitar aprobación humana.
- Contactar al prospecto únicamente cuando exista aprobación.
- Garantizar trazabilidad y resiliencia del workflow.

---

## Arquitectura

```text
Webhook
   │
Validación de Datos
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
```

---

## Tecnologías

- n8n Cloud
- OpenRouter
- Airtable
- Gmail
- Slack
- HTTP Webhooks
- JavaScript

---

## Base de Datos

### Tablas
- Prospectos
- Oportunidades
- Clientes
- Actividades
- Productos

### Campos principales
- Empresa
- Contacto
- Email
- Prioridad
- Clasificación IA
- Score IA
- Resumen IA
- Acción recomendada
- Estado de aprobación
- Fecha de aprobación

---

## Human-in-the-Loop

El workflow utiliza el nodo **Gmail – Send and Wait** para detener la ejecución hasta que la Gerencia apruebe o rechace el prospecto.

---

## Gestión de errores y resiliencia

- Validación previa de datos.
- Rutas específicas de error.
- Gestión explícita de errores de OpenRouter.
- Registro de incidencias en Airtable.
- Notificaciones automáticas por Slack.
- Finalización controlada del workflow.
- Reprocesamiento manual cuando sea necesario.

---

## Seguridad

Las credenciales de OpenRouter, Airtable, Gmail y Slack se administran mediante el sistema de credenciales de n8n. El workflow exportado no contiene API Keys ni credenciales en texto plano.

---

## Estructura del repositorio

```text
/
├── README.md
├── docs/
│   ├── Memoria_Tecnica.pdf
│   ├── Manual_Tecnico.pdf
│   ├── Manual_Usuario.pdf
│   ├── Documento_Resiliencia.pdf
│   ├── Matriz_Costos.pdf
│   ├── Comparativa_Modelos_IA.pdf
│   ├── Guia_Estructura_Repositorio.pdf
│   └── Diagrama_Arquitectura.pdf
├── workflow/
│   └── PROTS_Pipeline_Comercial_IA.json
├── evidencias/
├── diagrams/
└── entregables/
```

---

## Enlaces del proyecto

- Repositorio GitHub: https://github.com/DanielG-1980/PROTS-AI-Automation
- Airtable (modo lectura): https://airtable.com/appVE7CMnAZF3f61F/shrqlWwoL8QzGGwCI

---

## Autor

**Daniel Gilardi**

Proyecto académico – Arquitectura de Flujos IA.
