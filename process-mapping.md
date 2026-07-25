## 🗺️ Process Mapping & Efficiency

### 🌊 Value Stream Mapping (VSM)
I utilize VSM to identify **Non-Value-Added (NVA)** steps in the software delivery lifecycle.
* **Goal:** Reduce "Lead Time" from Requirement Discovery to Production Commit.
* **Focus:** Identifying bottlenecks in the validation iterations to increase velocity.

### 🏊 Swimlane (Cross-Functional) Diagram
Used to clarify hand-offs between departments:
* **Lane 1 (Stakeholders):** Business Requirements & UAT.
* **Lane 2 (PMO/Hasan):** 8/80 Governance & Resource Coordination.
* **Lane 3 (Engineering):** Code Development & Unit Testing.
* **Lane 4 (QA):** Final Validation & SLA Verification.

```mermaid
graph TD
    subgraph "CROSS-FUNCTIONAL DELIVERY FLOW"
    
    %% Lanes
    direction LR
    
    subgraph Stakeholders ["1. STAKEHOLDERS (Business)"]
        A[Business Requirement] --> B[Budget Approval]
        L[UAT Sign-off] --> M[Project Closure]
    end
    
    subgraph PMO ["2. PMO & GOVERNANCE (Hasan)"]
        B --> C{8/80 Rule Review}
        C -- "> 80h" --> D[Re-scope / SteerCo]
        C -- "< 80h" --> E[Resource Allocation]
        D --> B
        J[Sprint Governance] --> K[RAID Log Review]
        K --> L
    end
    
    subgraph Engineering ["3. ENGINEERING & DEV"]
        E --> F[Discovery/Wireframes]
        F --> G[Code Commit/Git]
        G --> H[CI/CD Pipeline]
    end
    
    subgraph QA ["4. QUALITY ASSURANCE"]
        H --> I[Automated Testing]
        I --> J
    end
    
    %% Formatting
    style C fill:#f9f,stroke:#333,stroke-width:2px
    style D fill:#f66,stroke:#333,stroke-width:2px
    style J fill:#6cf,stroke:#333,stroke-width:2px
    end
```

### 📈 Control Charts
Used to monitor process stability (e.g., tracking the number of bugs per sprint). If a data point falls outside **Upper/Lower Control Limits**, I initiate a **Fishbone RCA**.
