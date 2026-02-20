# Functional Requirements Document (FRD)

**Project:** Apparel Inventory Architecture & Logistics Optimization  
**Client:** Irish Heritage (Dublin, Ireland)  
**Lead Consultant:** Hasan Farooqui  
**Repository:** PMO-Governance-Toolkit  
**Status:** Implementation & Validation Phase  

---

## 1. Executive Summary
Irish Heritage required a modernization of their legacy inventory system to support growing B2B demand and retail complexity. This FRD outlines the transition from a "flat" inventory structure to a multi-dimensional, bin-managed architecture in Dynamics 365 Business Central.

## 2. Business Requirements & Technical Solutions
The project focused on three core pillars:
* **Granular Visibility:** Transitioning from single SKUs to a Variant Matrix (Size/Color/Gender).
* **Warehouse Control:** Implementing Directed Bins to eliminate picking errors and lost stock.
* **Cost Accuracy:** Utilizing Assembly BOMs to factor labor and packaging into the landed cost.

## 3. Implementation Logic & Technical Evidence
Technical proof is hosted in the `PMO-Governance-Toolkit` repository.

### Phase A: Master Data & Governance
* **Schema Design:** Defined the hierarchical structure for Item Attributes.
* **Categorization:** Grouped inventory to streamline financial reporting and filtering.
* **Variant Mapping:** Established the matrix for the apparel line (e.g., Guinness Heritage T-Shirt).

### Phase B: Logistics & Finance
* **Location Setup:** Configured the Dublin Warehouse (DUB-WH) with "Bin Mandatory" logic.
* **Financial Control:** Defined Inventory Posting Groups to ensure real-time G/L accuracy.
* **Validation:** Conducted stock take audits to verify 100% physical-to-system alignment.

### Phase C: Advanced SCM & Fulfillment (Work in Progress)
* **Bulk Order Strategy:** [Pending Training Screenshot - Special Order Linking]
* **Value-Added Services:** [Pending Training Screenshot - Assembly BOM & Labor Resources]

## 4. Operational Sign-off
The implementation successfully enables Irish Heritage to scale their B2B operations while maintaining 100% financial and physical stock accuracy. The architecture is validated for Dublin-wide distribution and high-volume fulfillment.

**End of Document**
