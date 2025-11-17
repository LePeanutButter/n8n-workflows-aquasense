# **Aqualia Global – n8n Workflows Versioning**

[![standard-readme compliant](https://img.shields.io/badge/readme%20style-standard-brightgreen.svg?style=flat-square)](https://github.com/RichardLitt/standard-readme)

A version-controlled repository for managing backup copies of all n8n workflows created for the academic automation project **Aqualia Global - Intelligent Water Management**, developed as part of the course **Estrategia de Operaciones y Procesos (PRI2IS)** at **Escuela Colombiana de Ingeniería Julio Garavito**.

This repository ensures traceability, reproducibility, and structured evolution of the Low-Code automation artifacts used to simulate SCADA, ERP, CRM, and GIS data consolidation through n8n, Supabase, Azure Free Tier, Grafana, and Gemini-based anomaly detection.

## **Table of Contents**

- [Background](#background)
- [Install](#install)
- [Usage](#usage)
  - [Workflow Structure](#workflow-structure)
- [Related Efforts](#related-efforts)
- [Maintainers](#maintainers)
- [License](#license)

## **Background**

This repository contains workflows developed for an academic simulation of Aqualia Global’s operations.

The project simulates data ingestion from SCADA, ERP, CRM, and GIS systems using Supabase tables. n8n acts as the orchestration engine for:

- automated data extraction, cleaning, and consolidation
- anomaly detection using Gemini AI
- workflow resilience through retries, error handling, and logging
- automated Grafana dashboard refreshes
- Teams/email alerts for anomalies or critical events

Keeping workflow backups in GitHub enables:

- versioning of automation artifacts
- rollback mechanisms
- team collaboration
- reproducibility for academic evaluation

## **Install**

This repository contains only exported workflow files (`.json`) and documentation.
To execute the workflows locally:

1. Install **Docker**
2. Run n8n:

   ```sh
   docker run -it --rm \
     -p 5678:5678 \
     -v ~/.n8n:/home/node/.n8n \
     n8nio/n8n
   ```

3. Import workflows from the n8n UI (`Settings -> Workflows -> Import`).

## **Usage**

Clone the repository:

```sh
git clone https://github.com/LePeanutButter/n8n-workflows-aqualia-global.git
```

Each workflow file follows the naming scheme:

```
workflowName_version.json
```

### **Workflow Structure**

Typical workflow components include:

- **Schedule Trigger** - periodic execution
- **Supabase nodes** - fetch SCADA/ERP/CRM/GIS data
- **Function nodes** - data merging and validation
- **AI API call** - anomaly detection (Gemini)
- **Supabase write-back** - store results and logs
- **Grafana Supabase metrics** - dataset refresh
- **Teams/Email notifications** - alerts and reporting

### **Documentation**

All reports and analysis documents are located in the [docs/](/docs/)
folder.

- [Informe de Análisis – Aqualia Global](/docs/analisis_sistemico_aqualia.pdf)

Additional documents will also be stored in this directory for easy reference.

> **Note:** All analysis reports are written in **Spanish**.

## **Related Efforts**

- [n8n Documentation](https://docs.n8n.io)
- [Supabase](https://supabase.com)
- [Grafana](https://grafana.com/)
- [System Thinking & Causal Loops](https://thesystemsthinker.com/)

## **Maintainers**

Primary contributors:

- [andrescalderonr](https://github.com/andrescalderonr) - Andrés Felipe Calderón
- [Lanapequin](https://github.com/Lanapequin) - Laura Natalia Perilla
- [lRicardol](https://github.com/lRicardol) - Ricardo Andrés Ayala
- [SantiagoAmaya21](https://github.com/SantiagoAmaya21) - Santiago Amaya
- [LePeanutButter](https://github.com/LePeanutButter) - Santiago Botero

## **License**

This repository is shared for **academic purposes** under the MIT License.
See the [`LICENSE`](/LICENSE) file for details.
