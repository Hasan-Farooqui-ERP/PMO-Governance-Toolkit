-- Identify incidents open for > 4 hours without a 'Working' status
-- Designed to trigger the Proactive Monitoring Dashboard
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

    ---

    -- Aggregating incident volume by County/Site to identify patterns
-- Used to populate the Power BI "Heat Map"
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
    COUNT(IncidentID) > 5 -- Filters for sites with recurring issues
ORDER BY 
    TotalIncidents DESC;

    ---

    -- Cross-referencing Warehouse Receipts with Invoice Ledger
-- Tier 4 Validation: Checking for Price/Quantity Mismatches
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
