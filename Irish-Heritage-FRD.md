# Functional Requirements Document (FRD)

**Project:** Apparel Inventory Architecture & Logistics Optimization  
**Client:** Irish Heritage (Dublin, Ireland)  
**Lead Consultant:** Hasan Farooqui  
**Repository:** PMO-Governance-Toolkit  
**Status:** Implementation & Validation Phase  

---

## 1. Executive Summary
Irish Heritage required a modernization of their legacy inventory system to support growing B2B demand and retail complexity. This FRD outlines the transition from a "flat" inventory structure to a multi-dimensional, bin-managed architecture in **Dynamics 365 Business Central**.

---

## 2. Business Requirements & Technical Solutions

| Requirement ID | Business Need | Technical Solution |
| :--- | :--- | :--- |
| **REQ-01** | SKU Rationalization | Attributes & Item Categories |
| **REQ-02** | Apparel Bifurcation | Multi-dimensional Variant Matrix |
| **REQ-03** | Warehouse Precision | Bin Mandatory & Location Governance |
| **REQ-04** | Financial Integrity | Automated Inventory Posting Setup |
| **REQ-05** | Audit Transparency | Reason Codes & Item Ledger Traceability |
| **REQ-06** | B2B Kitting/Logistics | Assembly BOMs & Special Order Linking |

---

## 3. Implementation Logic & Technical Evidence

*Technical proof is hosted in the [D365-Business-Central-Functional-Portfolio](https://github.com/Hasan-Farooqui-ERP/D365-Business-Central-Functional-Portfolio) repository.*

### Phase A: Master Data & Governance
* **Schema Design:** [Item Attributes & Data Governance](https://github.com/Hasan-Farooqui-ERP/D365-Business-Central-Functional-Portfolio/blob/main/03-Apparel-Inventory-Optimization/images/01-Functional-Data-Schema-Attributes.JPG)
* **Categorization:** [Item Category Hierarchy](https://github.com/Hasan-Farooqui-ERP/D365-Business-Central-Functional-Portfolio/blob/main/03-Apparel-Inventory-Optimization/images/02-Item-Category-Hierarchy-Setup.JPG)
* **Variant Mapping:** [Size & Gender Variant Matrix](https://github.com/Hasan-Farooqui-ERP/D365-Business-Central-Functional-Portfolio/blob/main/03-Apparel-Inventory-Optimization/images/04-Multi-Dimensional-Variant-Matrix.JPG)

### Phase B: Logistics & Finance
* **Location Setup:** [DUB-WH Greenfield & Bin Configuration](https://github.com/Hasan-Farooqui-ERP/D365-Business-Central-Functional-Portfolio/blob/main/03-Apparel-Inventory-Optimization/images/05-Greenfield-Location-Setup-Bin-Mandatory.JPG)
* **Financial Control:** [General Ledger Inventory Posting Setup](https://github.com/Hasan-Farooqui-ERP/D365-Business-Central-Functional-Portfolio/blob/main/03-Apparel-Inventory-Optimization/images/08-Inventory-Financial-Posting-Groups.JPG)
* **Validation:** [Item Ledger Audit Trail Verification](https://github.com/Hasan-Farooqui-ERP/D365-Business-Central-Functional-Portfolio/blob/main/03-Apparel-Inventory-Optimization/images/10-Item-Ledger-Audit-Trail.JPG)

### Phase C: Advanced SCM & Fulfillment (Work in Progress)
* **Bulk Order Strategy:** *[Pending Training Screenshot - Special Order Linking]*
* **Value-Added Services:** *[Pending Training Screenshot - Assembly BOM & Labor Resources]*

---

## 4. Operational Sign-off
The implementation successfully enables Irish Heritage to scale their B2B operations while maintaining 100% financial and physical stock accuracy. The architecture is validated for Dublin-wide distribution and high-volume fulfillment.

---
*End of Document*
