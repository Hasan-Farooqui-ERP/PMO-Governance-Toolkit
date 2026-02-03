## 📊 Engineering Health Metrics

### 🕒 Reliability Formulas
* **MTTF (Mean Time to Failure):** Total Operating Time / # of Failures. 
  * *Goal: Maximize for system stability.*
* **MTTR (Mean Time to Repair):** Total Maintenance Time / # of Repairs. 
  * *Goal: Minimize to meet SLA targets (90%+).*

### 🐟 Fishbone Diagram (RCA Structure)
When a system failure occurs, we analyze:
1. **Methods:** Was the 8/80 rule bypassed?
2. **Machines:** Are Azure/AWS instances throttled?
3. **Manpower:** Was there a training gap in D365 logic?
4. **Materials:** Was the legacy data corrupted at Tier 7?
