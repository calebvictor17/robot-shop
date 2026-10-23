### 2. The Blameless Postmortem Template (`docs/POSTMORTEM_TEMPLATE.md`)
This template will be used for **Step 6** after you execute your self-initiated chaos drill.

# Blameless Incident Postmortem: [Incident Title]

* **Date:** [YYYY-MM-DD]
* **Author:** Levi Thunderstorm
* **Status:** Complete

## Incident Summary
[Brief description of what broke, how long it lasted, and the impact on the user experience.]

## Timeline
* **[HH:MM]** - Monitoring alert `RobotShopHighErrorRateSLOBurn` fired in Slack.
* **[HH:MM]** - Engineer acknowledged alert and opened Grafana RED dashboard, isolating error to the `[Service Name]` microservice.
* **[HH:MM]** - Root cause identified via Loki logs ([Insert specific error message]).
* **[HH:MM]** - Mitigation applied ([Rollback / Pod restart / Config fix]).
* **[HH:MM]** - Traffic normalized; error rate dropped below 1% SLO threshold. Total downtime: [X minutes].

## Root Cause Analysis
[Detailed explanation of why the failure occurred—e.g., incorrect environment variable, database timeout, network partition.]

## Corrective & Preventive Action Items
| Action Item | Type | Owner | Target Date |
| :--- | :--- | :--- | :--- |
| Update automated health check probes | Prevention | SRE | [Date] |
| Refine Prometheus alert threshold window | Detection | SRE | [Date] |