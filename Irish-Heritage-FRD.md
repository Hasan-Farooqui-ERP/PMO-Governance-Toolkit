# Project: Apparel Inventory Architecture & Logistics Optimization

# Client: Irish Heritage (Dublin, Ireland)

# Consultant: Hasan Farooqui

# System: Dynamics 365 Business Central

# Status: Implementation & Validation Phase

## 1. Executive Summary
Irish Heritage, a premier apparel retailer in Dublin, faced critical operational challenges due to an outdated "flat" inventory structure. The legacy system lacked the granularity to track stock by **Size**, **Gender**, and **Bin Location**, leading to:

**Stock-outs:** Popular sizes were unavailable despite "Global" stock being positive.

**Financial Blind Spots:** Inaccurate inventory valuation on the Balance Sheet.

**Logistical Confusion:** No visibility into store returns or bulk B2B orders (e.g., University contracts).

**The Solution:** A full re-architecture of the D365 Business Central environment, implementing Multi-dimensional Variants, Bin Mandatory Governance, and Automated Financial Posting Groups.

## 2. Business Requirements & Technical Solutions

## 3. Step-by-Step Implementation Guide (Portfolio Evidence)
When viewing the repository 03-Apparel-Inventory-Optimization, follow this logic:

## **Phase A:** Master Data & Governance

**Step 1 (JPG 01-03):** Establish the "Master Item." We move from generic descriptions to Data-driven attributes.

**Step 2 (JPG 04 & 11):** The Financial Engine. We map the item to the G/L using FIFO costing and Posting Groups. This ensures the Accountant's reports match the Warehouse reports.

**Step 3 (JPG 05):** Generate the Variant Matrix. This is the core solution for the "Irish Heritage" size-tracking pain point.

## Phase B: Physical Operations
**Step 4 (JPG 06-07):** Configure the Greenfield Location. By setting "Bin Mandatory," we force the system to know the exact shelf (S-01-M) where the stock sits.

**Step 5 (JPG 08-09):** The Transaction Proof. We use an Item Journal to simulate a "Shop Return." By selecting the Reason Code, we provide "Why" the stock is back.

## Phase C: Advanced Logistics (Current Focus)
**Step 6 (JPG 10):** The Audit Trail. The Item Ledger Entry (ILE) is the final receipt that proves all the governance above worked perfectly.

**Step 7 (JPG 12-13):** Bulk Fulfillment. We create a Special Order for 500 units (University batch) to prove we can segregate B2B demand from everyday retail sales.

## 4. Project Outcome
100% Stock Visibility: Every item is now tracked by Size, Color, and Shelf.

**Reduced Over-ordering:** SKU-level planning ensures we only buy what is needed for specific locations.
**Automated Finance:** Manual month-end reconciliations are reduced as the G/L updates in real-time with every warehouse post.
