# 📖 Incident Runbook: Robot Shop SRE Core

## Alert: `RobotShopHighErrorRateSLOBurn`
* **Severity:** Critical
* **Symptom:** Error rate across focus services (`web`, `catalogue`, `cart`, `payment`) exceeds 1% over a 5-minute rolling window.

---

## 🛠️ Step-by-Step Mitigation & Troubleshooting

### Step 1: Identify the Failing Service
1. Open Grafana and navigate to your **RED Metrics Dashboard**.
2. Check the **Error Rate** panel to isolate *which* specific microservice is spiking (e.g., `payment` vs `catalogue`).

### Step 2: Inspect Logs for Root Cause
1. Open Grafana Loki or run `kubectl logs` filtered by the failing service and error level:
   ```bash
   kubectl logs -n robot-shop -l service=<failing-service> --tail=100