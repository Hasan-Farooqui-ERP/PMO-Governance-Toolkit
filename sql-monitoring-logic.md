# ERP & Incident Monitoring SQL Logic
**Project:** Proactive System Governance & SLA Management

---

### 1. Proactive SLA Breach Monitor
*Identifies incidents open for > 4 hours without a 'Working' status to trigger the Proactive Monitoring Dashboard.*

```sql
SELECT 
    IncidentID, 
    SiteLocation, 
    CreatedDate, 
    DATEDIFF(hour, CreatedDate, GETDATE()) AS HoursOpen 
FROM 
    IncidentRegistry 
WHERE 
    Status = 'Pending' 
    AND ResolutionStatus IS NULL 
    AND DATEDIFF(hour, CreatedDate, GETDATE()) > 4 
ORDER BY 
    HoursOpen DESC;
```


### 2. Used to populate the Power BI dashboard to identify site-specific recurring issues.
---
```sql
SELECT 
    SiteLocation, 
    COUNT(IncidentID) AS TotalIncidents, 
    AVG(DATEDIFF(minute, CreatedDate, ResolvedDate)) AS AvgResolutionTime 
FROM 
    IncidentRegistry 
WHERE 
    CreatedDate >= DATEADD(day, -30, GETDATE()) 
GROUP BY 
    SiteLocation 
HAVING 
    COUNT(IncidentID) > 5 
ORDER BY 
    TotalIncidents DESC;
```



### 3. Cross-referencing Warehouse Receipts with the Invoice Ledger to flag price/quantity mismatches.
---

```sql
SELECT 
    grn.PurchaseOrderID, 
    grn.QuantityReceived, 
    inv.QuantityInvoiced, 
    (grn.QuantityReceived - inv.QuantityInvoiced) AS Discrepancy 
FROM 
    Warehouse_GRN grn 
JOIN 
    Finance_Invoices inv ON grn.PurchaseOrderID = inv.PurchaseOrderID 
WHERE 
    grn.QuantityReceived <> inv.QuantityInvoiced 
    AND grn.Status = 'Posted';
```
---
