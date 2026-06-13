# smart_warehouse_shipment_delay_prediction

This repository stores notes and outputs for a DACON competition run driven by Auto_Dacon.

- Competition: https://dacon.io/competitions/official/236696/overview/description
- Metric: MAE
- Target: `avg_delay_minutes_next_30m`

## Run with Auto_Dacon

This repository stores the competition-specific data and metadata. Run the agent from
the reusable Auto_Dacon repository:

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
