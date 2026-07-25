# ERP & Incident Monitoring SQL Logic

Illustrative SQL patterns representing the type of monitoring, reporting, and reconciliation logic I have specified for technical teams to implement across ERP support and infrastructure monitoring roles. These are not verbatim production queries from a single employer, but patterns reflecting real requirements I have defined based on hands-on coordination with technical teams.


---

### 1. Proactive SLA Breach Monitor

* Identifies incidents open for more than a defined threshold (e.g. 4 hours) without an active resolution status, to support proactive monitoring workflows.

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

* Aggregates incident volume and average resolution time by site over a rolling 30-day window, used to populate a recurring-issue report and identify problem locations.
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

* A three-way-match pattern flagging quantity or price discrepancies between warehouse receipts and invoices, reflecting Procure-to-Pay control logic from ERP functional work.
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
