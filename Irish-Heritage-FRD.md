# Functional Requirements Document (FRD)

**Project:** Apparel Inventory Architecture & Logistics Optimization

**Client:** Irish Heritage (Dublin, Ireland)

**Consultant:** Hasan Farooqui

**System:** Dynamics 365 Business Central

**Status:** Implementation & Validation Phase

## 1. Executive Summary
**Irish Heritage**, a premier apparel retailer in Dublin, faced critical operational challenges due to an outdated "flat" inventory structure. The legacy system lacked the granularity to track stock by **Size, Gender, and Bin Location**, leading to stock-outs of popular items and financial reconciliation gaps.

**The Solution:** A full re-architecture of the D365 Business Central environment, implementing Multi-dimensional Variants, Bin Mandatory Governance, Automated Financial Posting Groups, and Assembly BOMs for B2B kitting.

## 2. Business Requirements & Technical Solutions

### **REQ-01: SKU Rationalization**

**Solution:** Attributes & Categories.

**Logic:** To prevent duplicate SKU creation and enable rich filtering for the web-shop.

### REQ-02: Apparel Bifurcation

**Solution:** Multi-dimensional Variants.

**Logic:** To track stock at the "Size/Gender" level (e.g., Men's Medium vs. Women's Small).

### REQ-03: Warehouse Precision

**Solution:** Location & Bin Mandatory.

**Logic:** To eliminate "Blind Spots" in the Dublin Warehouse (DUB-WH).

### REQ-04: Financial Integrity

**Solution:** Inventory Posting Setup.

**Logic:** To automate the link between physical stock and G/L Inventory Assets.

### REQ-05: Audit Transparency

**Solution:** Reason Codes.

**Logic:** To differentiate between New Arrivals and Store Returns.

### REQ-06: Bulk B2B Fulfillment

**Solution:** Special Order Linking & Lead Time Governance.

**Logic:** To "earmark" 500 units for Trinity College without affecting retail shelf stock.

### REQ-07: Light Manufacturing (Kitting)

**Solution:** Assembly BOMs with Resource Integration.

**Logic:** To manage "Value Added Services" (Gift Boxing) and track Labor Costs via Resources.

## 3. Implementation Logic (Portfolio Evidence)
Refer to the **/03-Apparel-Inventory-Optimization** repository for JPG evidence.

### Phase A: Master Data & Governance
**Step 1 (JPG 01-03):** Establish the "Master Item" with Data-driven attributes.

**Step 2 (JPG 04 & 11):** Financial Mapping to ensure Balance Sheet accuracy.

**Step 3 (JPG 05):** Generate the Variant Matrix to solve size-tracking issues.

### Phase B: Physical Operations & Logistics
**Step 4 (JPG 06-07):** Configure the Greenfield Location with "Bin Mandatory" tracking.

**Step 5 (JPG 08-09):** Validation using an Item Journal with a Reason Code.

**Step 6 (JPG 12):** Bulk Fulfillment. Linking Sales to Supply via Special Orders.

### Phase C: Production & Costing
**Step 7 (JPG 13):** Assembly BOM Setup. Integrating Items (Gift Boxes) and Resources (Labor) to calculate total landed cost per unit for B2B orders.

**Step 8 (JPG 10):** The Audit Trail. The Item Ledger Entry (ILE) proves the end-to-end governance worked.

### 4. Project Outcome
**100% Stock Visibility:** Every item is tracked by Size, Color, and Shelf.

**Cost Accuracy:** Labor and packaging costs are captured via Assembly orders.

**SCM Scalability:** System architecture is ready for B2B expansion and advanced lead-time planning.
