# smart_warehouse_shipment_delay_prediction

This repository stores one DACON competition project.

Reusable engine repository:
https://github.com/UnJung-Baek/Auto_Dacon

This project repository contains only the competition-specific metadata, context,
data files, notes, and local outputs for the smart warehouse competition.

- Competition: https://dacon.io/competitions/official/236696/overview/description
- Metric: MAE
- Target: `avg_delay_minutes_next_30m`

## Run with Auto_Dacon

Run the reusable Auto_Dacon engine from its own repository:

```powershell
git clone https://github.com/UnJung-Baek/Auto_Dacon.git
cd Auto_Dacon
py -3.11 auto_dacon.py bootstrap
$env:OPENROUTER_API_KEY="..."

.\.venv-agentk\Scripts\python.exe auto_dacon.py build-aide-rag `
  --rag-path "C:\Auto_Dacon_RAG\kaggle_cases_db"

.\.venv-agentk\Scripts\python.exe auto_dacon.py run-project `
  --project-dir "C:\path\to\Smart-Warehouse-Shipment-Delay-Prediction" `
  --workspace-name "C:\Auto_Dacon_Workspace" `
  --output-root "C:\Auto_Dacon_Outputs" `
  --enable-agent-rag `
  --agent-rag-path "C:\Auto_Dacon_RAG\kaggle_cases_db"
```

The expected output is:

```text
C:\Auto_Dacon_Outputs\smart_warehouse_shipment_delay_prediction\submission.csv
```

## Fallback Baseline

The preferred path is the full Agent_K/Auto_Dacon run above. If the Windows RAMP
race stalls, use the portable LightGBM fallback only to get a submit-ready file:

```powershell
.\.venv-agentk\Scripts\python.exe auto_dacon.py baseline-project `
  --project-dir "C:\path\to\Smart-Warehouse-Shipment-Delay-Prediction" `
  --output-root "C:\Auto_Dacon_Outputs" `
  --max-cpu 4
```

Latest known fallback result:

- File: `outputs/submission_latest.csv`
- Public score: `11.2360866528`
