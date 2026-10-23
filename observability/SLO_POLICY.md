# Service Level Objective (SLO) & Error Budget Policy

## 1. Objective
Maintain high availability and core operational performance for the primary e-commerce workflows of **Stan's Robot Shop**, specifically targeting the following core services:
* `web` (Frontend User Interface)
* `catalogue` (Product Catalog Service)
* `cart` (Shopping Cart Service)
* `payment` (Payment Gateway Integration)

---

## 2. Service Level Target (SLO)
* **Metric:** Percentage of successful HTTP requests (non-5xx responses) measured at the ingress gateway.
* **Target:** **99.9%** successful HTTP requests.
* **Measurement Window:** 30-day rolling window.

---

## 3. Error Budget Calculation
The Error Budget represents the maximum allowable failure rate before engineering priorities must pivot to stability:

$$\text{Error Budget} = 100\% - 99.9\% = 0.1\%$$

$$\text{Total Permitted Failed Requests} = 0.1\% \times \text{Total Monthly Requests}$$

---

## 4. Error Budget Exhaustion Policy
In the event that the 30-day Error Budget is exhausted prior to the standard window reset:

1. **Feature Freeze:** All non-critical feature releases, enhancements, and deployments across affected microservices are frozen immediately.
2. **Resource Realignment:** Engineering capacity must pivot 100% toward reliability engineering, infrastructure remediation, root cause analysis, and bug fixes.
3. **Thawing Protocol:** Normal deployment schedules will only resume once the rolling 30-day error budget rises back above the critical threshold and operational stability is confirmed.