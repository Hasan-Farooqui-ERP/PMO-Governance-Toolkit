# ERP Functional Specification Document (FSD)
## Module: Supply Chain & Inventory Traceability
**Version:** 1.0  
**Status:** Draft / For Review

---

## 1. Requirement Overview
**Business Objective:** To implement a mandatory 7-tier validation gate for all Goods Received Notes (GRN) to ensure ISO 9001 compliance before inventory is "Live" for Production Planning (MRP).

## 2. Stakeholders
* **Process Owner:** Supply Chain Manager
* **Technical Lead:** ERP Functional Analyst
* **Users:** Warehouse Operatives, Quality Lab Technicians

## 3. Functional Requirements (User Stories)
| ID | User Story | Priority | Acceptance Criteria |
| :--- | :--- | :--- | :--- |
| FR-01 | As a Warehouse User, I want the system to block GRN posting if the Vendor ISO certificate is expired. | High | System check against Vendor Master Data 'Expiry' field. |
| FR-02 | As a Quality Manager, I want a "Quality Hold" status applied automatically upon receipt. | Critical | Inventory status = 'Q-Hold' until manual QM release. |

## 4. Technical Logic & Data Mapping
* **Source Table:** `PurchLine` / `VendTable`
* **Trigger:** On Action `Post GRN`
* **Logic:** If `VendTable.ISOCertStatus` != 'Active', throw Error: "Vendor Compliance Failure."

## 5. UAT & Validation Steps (Tier 3)
1. Initiate PO for Vendor X.
2. Attempt GRN receipt.
3. Verify that Inventory remains in 'Blocked' status until QM parameters are entered.

---
*Developed by Hasan - ERP Functional Governance Framework*
