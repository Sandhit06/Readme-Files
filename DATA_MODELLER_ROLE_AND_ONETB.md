# 🧠 Data Modeller — Role, Responsibilities & Contribution to OneTB

> **Audience:** Anyone joining the OneTB programme — developers, analysts, business stakeholders, or new data modellers.
> **Purpose:** A complete reference on what a data modeller does, how the role varies, and precisely how data modellers power the OneTB platform — especially DQ rule linkages, metadata, and data governance.

---

## 📌 Table of Contents

1. [What Is a Data Modeller?](#1-what-is-a-data-modeller)
2. [The Three Hats of a Data Modeller](#2-the-three-hats-of-a-data-modeller)
3. [The 4-Layer Modelling Hierarchy (CDM → LDM → PDM → TDM)](#3-the-4-layer-modelling-hierarchy)
4. [Day-to-Day Work of a Data Modeller](#4-day-to-day-work-of-a-data-modeller)
5. [How the Role Varies — Junior vs Senior vs Architect](#5-how-the-role-varies)
6. [Data Modellers in the OneTB Platform — The Big Picture](#6-data-modellers-in-the-onetb-platform)
7. [Rosetta — The Data Modeller&#39;s Primary Workspace](#7-rosetta--the-data-modellers-primary-workspace)
8. [How Data Modellers Power DQ Rule Linkages (DQMA)](#8-how-data-modellers-power-dq-rule-linkages)
9. [The Full Governance Lifecycle (Modelling → DQ → Monitoring)](#9-the-full-governance-lifecycle)
10. [Code Snippets — What the Backend Looks Like](#10-code-snippets--what-the-backend-looks-like)
11. [Tools, Skills &amp; Techniques](#11-tools-skills--techniques)
12. [Key Terminology Glossary](#12-key-terminology-glossary)
13. [Common Anti-Patterns &amp; What Data Modellers Prevent](#13-common-anti-patterns--what-data-modellers-prevent)
14. [Career Growth Path](#14-career-growth-path)

---

## 1. What Is a Data Modeller?

A **Data Modeller** is a specialist who designs the structure, meaning, and relationships of data within an organisation. They are the **architects of how data is organised, named, described, and connected** — at every level from high-level business concepts down to the actual database columns.

> **Simple analogy:** Think of a city planner. Before any building is constructed, the planner draws blueprints — where roads go, how zones connect, what each building is for. A data modeller does exactly that, but for data. They draw the "blueprint" of a bank's data before any code is written or database table is created.

Without data modellers:

```
❌  Developers call the same concept different things in different systems
    → "CUST_ID" in System A, "CUSTOMER_NUMBER" in System B, "CLI_REF" in System C
    → Nobody knows they are the same thing

❌  A regulator asks "what data does the bank hold on customers?"
    → Nobody can answer because there is no map

❌  A data quality rule is applied to the wrong column
    → Thousands of false alerts flood operations teams

❌  A new system is built that duplicates existing data
    → Causes inconsistency, auditing failures, increased cost
```

With data modellers:

```
✅  One canonical name, definition, and description per concept
✅  A clear map from business language → technical implementation
✅  DQ rules attached to the correct, authoritative attributes
✅  Regulatory questions answered with traceable lineage
✅  New systems built to integrate cleanly with existing structures
```

---

## 2. The Three Hats of a Data Modeller

A data modeller can wear different "hats" depending on the context. In OneTB, all three are relevant:

```
┌─────────────────────────────────────────────────────────────────────┐
│  HAT 1: BUSINESS TRANSLATOR                                         │
│  ─────────────────────────────────────────────────────────────────  │
│  Sits with business analysts and stakeholders                       │
│  Asks: "What does 'Customer' mean to you? Is a prospect a          │
│         customer? What about a former customer?"                    │
│  Creates the Conceptual Model (CDM) — plain-language concepts       │
│                                                                     │
│  HAT 2: STRUCTURAL DESIGNER                                         │
│  ─────────────────────────────────────────────────────────────────  │
│  Works with architects and senior analysts                          │
│  Designs: entities, attributes, keys, cardinalities, constraints   │
│  Creates the Logical Model (LDM) — database-agnostic blueprint     │
│                                                                     │
│  HAT 3: TECHNICAL IMPLEMENTER                                       │
│  ─────────────────────────────────────────────────────────────────  │
│  Collaborates with DBAs and engineers                               │
│  Maps LDM to specific database technology (Oracle, Teradata, etc.) │
│  Creates the Physical Model (PDM) — actual tables and columns      │
└─────────────────────────────────────────────────────────────────────┘
```

---

## 3. The 4-Layer Modelling Hierarchy

This is the core technical framework that data modellers work within. OneTB's **Rosetta** module is built entirely around this four-layer hierarchy.

```
┌────────────────────────────────────────────────────────────────────────────┐
│                     THE 4-LAYER DATA MODELLING STACK                       │
│                                                                            │
│  LAYER 1: CONCEPTUAL DATA MODEL (CDM)                                      │
│  ──────────────────────────────────────────────────────────────────────    │
│                                                                            │
│  PURPOSE: Define WHAT business things exist — no technical detail          │
│  AUDIENCE: C-suite, regulators, business owners, product managers          │
│  DETAIL:   Very low (just names and relationships)                         │
│                                                                            │
│  Example:                                                                  │
│   Subject Area: "Transactional Banking"                                   │
│     └─ Concept: "Customer"                                                │
│         └─ relates to → "Account"                                         │
│         └─ relates to → "Transaction"                                     │
│                                                                            │
│  In OneTB Rosetta:  /explore/metadata/conceptualModel                     │
│  Excel columns:  SubjectArea | ConceptName | Definition | Relationship     │
│                                                                            │
├────────────────────────────────────────────────────────────────────────────┤
│                                                                            │
│  LAYER 2: LOGICAL DATA MODEL (LDM)                                         │
│  ──────────────────────────────────────────────────────────────────────    │
│                                                                            │
│  PURPOSE: Define HOW things are structured — attributes + relationships    │
│  AUDIENCE: Data architects, data modellers, senior analysts                │
│  DETAIL:   Medium (entities, attributes, data types, cardinalities)        │
│                                                                            │
│  Example:                                                                  │
│   Logical Entity: "Customer"                                              │
│     ├─ Attribute: "Customer ID"         (STRING, NOT NULL, PK)            │
│     ├─ Attribute: "Customer Full Name"  (STRING, NOT NULL)                │
│     ├─ Attribute: "Date of Birth"       (DATE)                            │
│     ├─ Attribute: "Country of Domicile" (STRING, 2-char ISO code)         │
│     └─ Attribute: "KYC Status"          (ENUM: VERIFIED | PENDING | FAIL) │
│   Relationship: Customer (1) ──── has many (N) ──── Account               │
│                                                                            │
│  In OneTB Rosetta:  /explore/metadata/logicalModel                        │
│  Excel columns:  EntityName | AttributeName | DataType | Cardinality |     │
│                  BusinessDefinition | PrimaryKey | ForeignKey              │
│                                                                            │
├────────────────────────────────────────────────────────────────────────────┤
│                                                                            │
│  LAYER 3: PHYSICAL DATA MODEL (PDM)                                        │
│  ──────────────────────────────────────────────────────────────────────    │
│                                                                            │
│  PURPOSE: The actual database implementation                               │
│  AUDIENCE: DBAs, engineers, ETL developers                                 │
│  DETAIL:   High (table names, column names, DB-specific types, indexes)    │
│                                                                            │
│  Example:                                                                  │
│   Physical Object: "CUST_MASTER"   (maps to LDM entity "Customer")        │
│     ├─ Column: "CUST_SK"      VARCHAR(20)    NOT NULL    PK               │
│     ├─ Column: "CUST_NM"      VARCHAR(100)   NOT NULL                     │
│     ├─ Column: "DOB_DT"       DATE                                         │
│     ├─ Column: "CTY_CD"       CHAR(2)                                      │
│     └─ Column: "KYC_STS_CD"   CHAR(1)       NOT NULL                      │
│   Source System: CORE_BANKING | Database: Oracle 19c | Schema: ADS         │
│                                                                            │
│  In OneTB Rosetta:  /explore/metadata/physicalModel                       │
│  Excel columns:  TableName | ColumnName | DataType | Length | Nullable |   │
│                  IsPrimaryKey | LinkedLDMAttribute | SourceSystem          │
│                                                                            │
├────────────────────────────────────────────────────────────────────────────┤
│                                                                            │
│  LAYER 4: TRANSFORMATION DATA MODEL (TDM)                                  │
│  ──────────────────────────────────────────────────────────────────────    │
│                                                                            │
│  PURPOSE: Show how data MOVES from source to target                        │
│  AUDIENCE: ETL engineers, data engineers, pipeline developers              │
│  DETAIL:   Very high (source/target mapping, formulas, derivation types)   │
│                                                                            │
│  Example:                                                                  │
│   Source:   SRC_CORE.RAW_CUSTOMER.CUSTOMER_ID                             │
│   Target:   ADS.CUST_MASTER.CUST_SK                                        │
│   Derivation Type: "Direct Copy"                                           │
│                                                                            │
│   Source:   SRC_CORE.RAW_CUSTOMER.BIRTH_DATE_RAW                          │
│   Target:   ADS.CUST_MASTER.DOB_DT                                         │
│   Derivation Type: "Calculated"                                            │
│   Formula:  CAST(BIRTH_DATE_RAW AS DATE FORMAT 'YYYY-MM-DD')              │
│                                                                            │
│  In OneTB Rosetta:  /explore/metadata/transformation                      │
│                                                                            │
└────────────────────────────────────────────────────────────────────────────┘
```

### Visual Flow Between Layers

```
         BUSINESS WORLD                         TECHNICAL WORLD
         ─────────────                          ───────────────

  [CDM] "Customer"    ──maps to──►  [LDM] "Customer Entity"
                                           │ has attribute
                                           ▼
                                    "Customer ID (STRING, PK)"
                                           │ implemented as
                                           ▼
                                    [PDM] "CUST_MASTER.CUST_SK"
                                           │ populated by
                                           ▼
                                    [TDM] SRC_CORE.RAW_CUSTOMER.CUSTOMER_ID
                                          → Direct Copy → CUST_MASTER.CUST_SK
```

---

## 4. Day-to-Day Work of a Data Modeller

### 🟦 Activity 1: Requirements Gathering

Before drawing a single box or arrow, a data modeller must interview stakeholders:

- **Business Analysts:** "What data flows through this process?"
- **Product Owners:** "What questions must we be able to answer from this data?"
- **DBAs:** "What constraints does the existing platform impose?"
- **Compliance Teams:** "What regulatory fields are mandatory?"

Questions a modeller always asks:

```
❓ What is the UNIQUE IDENTIFIER for this entity?
❓ What is the RELATIONSHIP between Entity A and Entity B?
   (1-to-1? 1-to-many? many-to-many?)
❓ Is this attribute MANDATORY or OPTIONAL?
❓ What are the ALLOWED VALUES for this attribute?
❓ Which SOURCE SYSTEM is the MASTER / authoritative source?
❓ How does this attribute CHANGE OVER TIME? (slowly changing dimension?)
❓ Do we need HISTORICAL DATA or just the latest snapshot?
```

---

### 🟦 Activity 2: CDM Creation — Business Blueprint

The first deliverable is a Conceptual Data Model. This is typically drawn in a tool and then exported to Excel for upload into OneTB Rosetta.

```
CDM Example — Transactional Banking Domain

Subject Area: Transactional Banking
│
├── Customer
│     relates to → Account         (type: Has)
│     relates to → Transaction     (type: Initiates)
│     relates to → KYC Record      (type: Has)
│
├── Account
│     relates to → Product         (type: Belongs To)
│     relates to → Transaction     (type: Records)
│
├── Transaction
│     relates to → Currency        (type: Denominated In)
│     relates to → Counterparty    (type: Involves)
│
└── Product
      relates to → Fee Schedule    (type: Has)
```

The data modeller uploads this into OneTB Rosetta via:

- Download the CDM Excel template → `/onetb/api/v1/rosetta/download/cdm`
- Fill in the template
- Upload → `/onetb/api/v1/rosetta/cdm/upload`
- The submission enters an approval workflow (PENDING → APPROVED → LIVE)

---

### 🟦 Activity 3: LDM Design — The Structural Blueprint

This is where the modeller specifies each attribute in detail. For OneTB, this means populating the LDM Excel template with entries like:

```
EntityName       | AttributeName        | DataType | Nullable | IsPK | Definition
─────────────────────────────────────────────────────────────────────────────────
Customer         | Customer ID          | STRING   | N        | Y    | Unique identifier for a customer...
Customer         | Customer Full Name   | STRING   | N        | N    | The full legal name of the customer
Customer         | Date of Birth        | DATE     | Y        | N    | The customer's date of birth (ISO format)
Customer         | Country of Domicile  | STRING   | N        | N    | ISO 2-letter country code of domicile
Account          | Account Number       | STRING   | N        | Y    | 10-digit unique account number
Account          | Account Status       | STRING   | N        | N    | ACTIVE | CLOSED | FROZEN
Account          | Account Open Date    | DATE     | N        | N    | Date the account was opened
Transaction      | Transaction ID       | STRING   | N        | Y    | Unique transaction reference number
Transaction      | Transaction Amount   | DECIMAL  | N        | N    | Gross amount of the transaction
Transaction      | Currency Code        | STRING   | N        | N    | ISO 3-letter currency code
```

Every attribute has a **business definition** — a critical data contract that ties the technical column to business meaning.

---

### 🟦 Activity 4: PDM Design — Technical Implementation

After LDM approval, the modeller works with DBAs to map each logical entity/attribute to the actual database technology:

```
LDM Entity: "Customer"          →   PDM Object: "CUST_MASTER"  (Oracle, schema: ADS)
LDM Attribute: "Customer ID"    →   PDM Column: "CUST_SK"      VARCHAR(20) NOT NULL PK
LDM Attribute: "Full Name"      →   PDM Column: "CUST_NM"      VARCHAR(100) NOT NULL
LDM Attribute: "Date of Birth"  →   PDM Column: "DOB_DT"       DATE
LDM Attribute: "Country Code"   →   PDM Column: "CTY_CD"       CHAR(2) NOT NULL
```

The modeller must understand database-specific constraints:

- Oracle VARCHAR2 vs Teradata VARCHAR
- Partitioning keys for performance
- Index strategies for query optimisation
- Nullable vs NOT NULL with default values

---

### 🟦 Activity 5: Review & Governance (Critical in OneTB)

All models go through a **4-eye approval process** in OneTB. The data modeller:

1. Submits the model via Excel upload
2. A **different** reviewer (not the same person) must approve it
3. Self-approval is technically blocked at the backend level
4. Once approved, the model is LIVE in Rosetta

```java
// From Rosetta Web Service — Self-approval is FORBIDDEN
// ModelUploadController.java
if (StringUtils.equals(bankId, uploadHistory.getCreatedBy())) {
    throw new OnetbException(USER_CAN_NOT_APPROVE_TEMPLATE_UPLOADED_BY_HIMSELF);
}
// This means you can never rubber-stamp your own work.
```

---

## 5. How the Role Varies

### Across Seniority Levels

```
┌────────────────────────────────────────────────────────────────────────────┐
│  JUNIOR DATA MODELLER (0–3 years)                                          │
│  ─────────────────────────────────────────────────────────────────────     │
│  What they do:                                                             │
│  • Maintain and update existing models (adding new attributes)             │
│  • Document business definitions for new columns                           │
│  • Run validation checks after uploads in Rosetta                          │
│  • Assist with DQ linkage — mapping rules to known attributes              │
│  • Create and manage PDM entries for new tables                            │
│  • Communicate with DBAs for physical model confirmations                  │
│                                                                            │
│  In OneTB:                                                                 │
│  • Uploads LDM/PDM Excel templates for new source system tables            │
│  • Creates basic linkage records in DQMA for standard rules                │
│  • Monitors the DQ Monitor dashboard for their domain                      │
│  • Raises exceptions when data quality drops below thresholds              │
│                                                                            │
├────────────────────────────────────────────────────────────────────────────┤
│                                                                            │
│  MID-LEVEL DATA MODELLER (3–6 years)                                       │
│  ─────────────────────────────────────────────────────────────────────     │
│  What they do:                                                             │
│  • Own specific business domains (e.g., Customer domain, Trade domain)     │
│  • Design Logical Models for new source systems end-to-end                 │
│  • Define Critical Data Elements (CDEs) — the most important attributes   │
│  • Work with data quality teams to define what "good data" looks like      │
│  • Drive the DQ rule linkage strategy for their domain                     │
│  • Review and approve junior modellers' work                               │
│  • Create Transformation Models showing ETL logic in metadata form         │
│                                                                            │
│  In OneTB:                                                                 │
│  • Manages the full CDM → LDM → PDM → TDM pipeline for their domain      │
│  • Designs the rule linkage strategy: which DQ rules apply to which CDEs  │
│  • Reviews DQ exception reports and drives resolution                     │
│  • Uses the Rosetta visualisation feature to review ER diagrams           │
│  • Works with DQMA tech team to configure rule scheduling                  │
│                                                                            │
├────────────────────────────────────────────────────────────────────────────┤
│                                                                            │
│  SENIOR / LEAD DATA MODELLER / DATA ARCHITECT (6+ years)                   │
│  ─────────────────────────────────────────────────────────────────────     │
│  What they do:                                                             │
│  • Set the enterprise data modelling standards and naming conventions      │
│  • Design the CDM architecture across all business domains                 │
│  • Govern the metadata management strategy (tools, processes, workflows)  │
│  • Work with regulators to map data to BCBS 239 / GDPR / local standards  │
│  • Evaluate new data model tools and frameworks                            │
│  • Define the DQ framework — which dimensions to measure, thresholds       │
│  • Advise on data vault, star schema, 3NF design trade-offs               │
│                                                                            │
│  In OneTB:                                                                 │
│  • Drives the OneTB Rosetta strategy and model evolution                  │
│  • Sets the rule category framework for DQMA (Completeness, Accuracy etc) │
│  • Defines the metadata governance SLA (how quickly models must be updated)│
│  • Liaises with security team on RBAC model access controls               │
│  • Advises on lineage graph design (end-to-end traceability chains)        │
└────────────────────────────────────────────────────────────────────────────┘
```

### Across Project Types

| Project Type                     | Focus                                          | Key Output                                 |
| -------------------------------- | ---------------------------------------------- | ------------------------------------------ |
| **New system onboarding**  | Map source tables to CDM/LDM/PDM               | Full model for the new source system       |
| **Regulatory reporting**   | Define canonical regulatory fields             | SSDR-compatible attribute definitions      |
| **Data quality programme** | Identify CDEs and define DQ rules              | Linkage of DQ rules to physical attributes |
| **Data migration**         | Map source-to-target with transformation logic | TDM (Transformation model)                 |
| **Analytics project**      | Define star/snowflake schema                   | Dimensional model (facts + dimensions)     |
| **Real-time pipeline**     | Model event schemas                            | Message schema definitions                 |

---

## 6. Data Modellers in the OneTB Platform — The Big Picture

OneTB has been built with data modellers as **first-class citizens**. Every major module relies on the work data modellers do.

```
┌──────────────────────────────────────────────────────────────────────────┐
│               HOW DATA MODELLERS FEED EVERY ONETB MODULE                 │
│                                                                          │
│  DATA MODELLER CREATES                  ENABLES IN ONETB                │
│  ──────────────────────────────────     ─────────────────────────────── │
│                                                                          │
│  CDM → LDM → PDM models                 Rosetta browse / search         │
│  (uploaded via Excel templates)          ER Diagram visualisation        │
│                                          Change log / audit trail        │
│                                                                          │
│  CDE (Critical Data Element)            DQMA Rule creation              │
│  identification within LDM              DQMA Linkage — attaches rules   │
│                                          to specific PDM columns         │
│                                                                          │
│  Transformation models (TDM)            Lineage graph                   │
│  (source → target mappings)              "Where does this data come from?"│
│                                                                          │
│  Business definitions on attributes     LDM additionalInfo endpoint     │
│                                          Tooltip/hover text in UI        │
│                                                                          │
│  Physical model accuracy                RTDS channel config validation   │
│  (correct table names + columns)         DQMA tech monitor (EOD PDM      │
│                                          exception checks)               │
│                                                                          │
│  Domain/subdomain classification        DQMA filter dropdowns           │
│                                          Exception workflow routing      │
│                                          Monitor dashboard segmentation   │
└──────────────────────────────────────────────────────────────────────────┘
```

The entire OneTB data governance platform runs on the foundation that data modellers build. Without accurate, up-to-date models in Rosetta, the DQ rules have nothing to link to, the lineage graph is incomplete, and the monitor dashboards show meaningless data.

---

## 7. Rosetta — The Data Modeller's Primary Workspace

**Rosetta** is the OneTB module built specifically for data modellers. It is accessible at `/explore/metadata` in the portal.

### 7.1 What Modellers Do in Rosetta

```
                    ROSETTA — DATA MODELLER WORKFLOW
                    ─────────────────────────────────

  BROWSE EXISTING MODELS                      UPLOAD NEW MODELS
  ─────────────────────                       ─────────────────

  1. Navigate to /explore/metadata            1. Download Excel template
  2. Select model type: CDM / LDM / PDM / TDM   (correct column headers)
  3. Filter by Business Domain                2. Fill in data offline
                Business Domain: CIB-TB-Cash  3. Upload file → backend validates
  4. Select Model Key                         4. Submission enters review queue
  5. Browse entities and attributes           5. Reviewer approves/rejects
  6. Click row → see full detail              6. Once APPROVED → data is LIVE
  7. See relationships / cardinality          7. Visible to all OneTB users
  8. See DQ rules linked to attribute
  9. See change history (who changed what)
```

### 7.2 The Upload → Approval Workflow

```
┌─────────────────────────────────────────────────────────────────┐
│          ROSETTA GOVERNANCE WORKFLOW (4-eye principle)          │
│                                                                 │
│  Step 1: DOWNLOAD TEMPLATE                                      │
│  ────────────────────────────                                   │
│  GET /onetb/api/v1/rosetta/download/{cdm|ldm|pdm|transformation}│
│  → Opens Excel with the correct column layout                   │
│                                                                 │
│  Step 2: FILL TEMPLATE                                          │
│  ────────────────────────────                                   │
│  Data modeller populates rows offline                           │
│  (entity names, attribute names, definitions, types, etc.)     │
│                                                                 │
│  Step 3: UPLOAD                                                 │
│  ────────────────────────────                                   │
│  POST /onetb/api/v1/rosetta/{type}/upload (multipart)          │
│  → Returns a taskId (UUID)                                      │
│  → Backend validates all rows against business rules            │
│                                                                 │
│  Step 4: MONITOR PROGRESS                                       │
│  ────────────────────────────                                   │
│  GET /onetb/api/v1/rosetta/upload/currentProgress/{taskId}     │
│  → Returns progress: 0% ... 100%                               │
│  → Errors listed per row if validation fails                   │
│                                                                 │
│  Step 5: APPROVAL (by a DIFFERENT person — 4-eye rule)         │
│  ────────────────────────────                                   │
│  POST /onetb/api/v1/rosetta/action/updateModelState            │
│  { id: 123, action: "APPROVE", type: "ldm" }                   │
│  → Status transitions: PENDING → IN_REVIEW → APPROVED → LIVE  │
│                                                                 │
│  ⚠️ Self-approval is BLOCKED in backend code:                  │
│  if (bankId == uploadHistory.getCreatedBy()) → THROW ERROR     │
└─────────────────────────────────────────────────────────────────┘
```

### 7.3 Visualisation — ER Diagrams

One of the most powerful features data modellers use is the **graph visualisation** in Rosetta. The backend builds a graph of nodes (entities/attributes) and relationships, which the frontend renders as an interactive ER diagram using D3.js and dagre-d3.

```
Backend graph response structure:
{
  "nodes": [
    { "id": "2187",  "labels": ["LogicalEntity"],    "properties": {"name": "Customer"}, "children": [...] },
    { "id": "2190",  "labels": ["LogicalEntity"],    "properties": {"name": "Account"},  "children": [...] },
    { "id": "33021", "labels": ["LogicalAttribute"], "properties": {"name": "Customer ID"} }
  ],
  "relationships": [
    {
      "type": "RELATION_TO",
      "startNodeId": "2187",
      "endNodeId": "2190",
      "properties": {
        "relationshipCount": 3,
        "relationships": [
          { "key": "FK#ACCT", "cardinalityAB": "One and only one", "cardinalityBA": "Zero or more" }
        ]
      }
    }
  ]
}
```

Node ID prefix convention prevents collisions:

```
"1" + entityId   →  ConceptualEntity   e.g., "1200"
"2" + entityId   →  LogicalEntity      e.g., "2187"
"3" + attrId     →  LogicalAttribute   e.g., "333051"
"3" + objectId   →  PhysicalObject     e.g., "3500"
"4" + attrId     →  PhysicalAttribute  e.g., "488001"
```

---

## 8. How Data Modellers Power DQ Rule Linkages

This is where data modellers make their **most direct impact** on data quality in OneTB. The DQMA (Data Quality Management & Analytics) module's entire usefulness depends on accurate, complete data models in Rosetta.

### 8.1 The Dependency Chain

```
DATA MODELLER DEFINES              ───►   DQ TEAM CAN NOW DO
───────────────────────────────────────────────────────────────────────────
LDM Attribute: "Customer ID"             Identify it as a CDE (Critical
  + definition: "Unique identifier..."   Data Element) requiring DQ checks
  + nullable: false
  + format: 10-digit alphanumeric
                          ▼
PDM Column: CUST_MASTER.CUST_SK          Create DQ Rules targeting this
  + dataType: VARCHAR(20)                exact physical column
  + nullable: NOT NULL
  + source system: CORE_BANKING
                          ▼
Transformation: RAW_CUSTOMER.CUSTOMER_ID  Link DQ rules to ALL columns in
  → CUST_MASTER.CUST_SK                   the lineage chain — not just one
  derivationType: Direct Copy
                          ▼
LINKAGE RECORD CREATED                   DQ rule now runs on real data
  CDE Rule: "Not Null Check"             DQ Monitor shows pass/fail %
  → CUST_MASTER.CUST_SK                  Exceptions raised when it fails
  → Status: LIVE
```

### 8.2 What Is a CDE (Critical Data Element)?

A **CDE** is a specific attribute in the logical model that has been flagged as **mission-critical**. Data modellers identify CDEs based on:

- **Business importance:** Used in key reports, client-facing data, regulatory reporting
- **Risk:** If wrong, leads to financial loss, compliance breach, customer harm
- **Volume:** Appears in millions of records and any error is magnified at scale

Examples of CDEs in a bank:

- Customer Account Number
- Transaction Amount
- Currency Code
- Customer Date of Birth (for age verification)
- Counterparty Legal Entity Identifier (LEI)
- Trade Settlement Date

Once a data modeller identifies a CDE, the DQ team creates DQ Rules and uses DQMA Linkage to attach those rules to the physical column.

### 8.3 The Linkage Record — Bridging Modelling and DQ

A **Linkage** record in DQMA is the direct product of the data modeller's PDM work. It connects a DQ Rule to a Physical Data Model attribute:

```typescript
// A Linkage record in the system:
type LinkageListItem = {
  // ← These come directly from the Data Modeller's PDM work ←
  cdeSourcingSystem?:           string;  // e.g., "CORE_BANKING"
  targetDataDomain?:            string;  // e.g., "Customer"
  sourceSystemName?:            string;  // e.g., "Core Banking System"
  targetLogicalEntityName?:     string;  // e.g., "Customer Master"    ← From LDM
  targetLogicalAttributeName?:  string;  // e.g., "Customer ID"        ← From LDM

  // ← These are what the DQ team fills in ←
  ruleMappingRuleDtoList?:      Rule[];  // DQ rules being applied
  liveStatus?:   'Review' | 'ReadyForRelease' | 'Live';
  jiraLink?:     string;                // Change management ticket
  jiraNum?:      string;                // ADO/Jira ticket number
};
```

The fields `targetLogicalEntityName` and `targetLogicalAttributeName` **directly reference the LDM that the data modeller created**. If the LDM is wrong, incomplete, or out of date, the linkage is pointing at invalid metadata.

### 8.4 Linkage Status Lifecycle — Where Data Modellers Are Involved

```
         ROLE:    Data Modeller    DQ Analyst    Data Steward    Approver
                        │               │              │              │
  CREATE LINKAGE         │               │              │              │
  Identify the CDE ──── ▼               │              │              │
  and the correct        │               │              │              │
  PDM column        DRAFT────────────────►─────────────►              │
                    (DQ analyst creates with DM's attribute info)       │
                                                        │              │
  REVIEW                                                ▼              │
  DM validates that                              REVIEW────────────────►
  the correct attr                              (submitted for         │
  is referenced                                  review)               │
                                                                        │
  APPROVAL                                                   READY FOR  │
  Another team member                                        RELEASE ───►
  (not the creator)                                           (RFR)     │
  approves it                                                            │
                                                                        ▼
                                                                       LIVE
                                                              (DQ rule is now
                                                               active on real data)
```

### 8.5 DQ Rule Categories — What Data Modellers Define

When a data modeller documents an LDM attribute, they indirectly define which **DQ rule categories** apply. Here is the mapping:

```
LDM Attribute Property          →   DQ Rule Category   →   What It Checks
──────────────────────────────────────────────────────────────────────────
nullable: false                 →   Completeness        →   Value is not null/blank
format: "YYYY-MM-DD" (DATE)     →   Validity            →   Date format is correct
allowedValues: [ISO codes]      →   Validity            →   Value is in allowed list
dataType: DECIMAL, length: 10,2 →   Accuracy            →   Number is within valid range
isPrimaryKey: true              →   Uniqueness          →   No duplicates exist
auditColumns: [CreatedBy, etc.] →   Audit               →   Audit metadata is populated
isActive: boolean               →   Boolean             →   Y/N or TRUE/FALSE only
```

The data modeller's metadata definitions are literally the **specification** from which DQ rules are written.

### 8.6 Domain / SubDomain Classification

In DQMA's Monitor and Exception modules, every DQ result is grouped by:

- `dataDomain` — e.g., "Customer", "Trade", "Cash Management"
- `subDomain`  — e.g., "Customer Master", "Customer KYC"

These domain and subdomain values **come from the LDM and PDM** that data modellers maintain. If a modeller assigns a wrong domain to a table, the monitor dashboard shows results in the wrong bucket.

```typescript
// DQMA Monitor record — domain values sourced from Rosetta metadata
type MonitorListItem = {
  dataDomain:    string;   // "Customer" ← must match LDM businessDomain
  subDomain:     string;   // "Customer Master" ← must match LDM sub-domain
  sourceSystem:  string;   // "CORE_BANKING" ← must match PDM source system
  entity:        string;   // "CUST_MASTER" ← must match PDM table name
  attribute:     string;   // "CUST_SK" ← must match PDM column name
  ruleCheckStatus: string; // "PASS" | "FAIL" | "WARN"
};
```

---

## 9. The Full Governance Lifecycle

This is the end-to-end journey from a business requirement to monitored data quality — with data modellers at every stage:

```
┌──────────────────────────────────────────────────────────────────────────────┐
│         FULL DATA GOVERNANCE LIFECYCLE IN ONETB                              │
│                                                                              │
│  PHASE 1: CONCEPTUAL MODELLING                                               │
│  ─────────────────────────────────────────────────────────────────────────   │
│  Who: Data Modeller + Business Analyst                                       │
│  What: Define business entities and their relationships                      │
│  Tool: Rosetta → CDM module                                                  │
│  Output: CDM with subject areas, concepts, and relationships                 │
│  API: POST /onetb/api/v1/rosetta/cdm/upload                                  │
│                                                                              │
│          │                                                                   │
│          ▼                                                                   │
│                                                                              │
│  PHASE 2: LOGICAL MODELLING                                                  │
│  ─────────────────────────────────────────────────────────────────────────   │
│  Who: Data Modeller + Data Architect                                         │
│  What: Expand CDM concepts into entities with attributes                     │
│  Tool: Rosetta → LDM module                                                  │
│  Output: LDM with all attributes, types, cardinalities, definitions          │
│  Key Decision: Which attributes are CDEs (Critical Data Elements)?           │
│  API: POST /onetb/api/v1/rosetta/ldm/upload                                  │
│                                                                              │
│          │                                                                   │
│          ▼                                                                   │
│                                                                              │
│  PHASE 3: PHYSICAL MODELLING                                                 │
│  ─────────────────────────────────────────────────────────────────────────   │
│  Who: Data Modeller + DBA                                                    │
│  What: Map logical attributes to actual database tables/columns              │
│  Tool: Rosetta → PDM module                                                  │
│  Output: PDM with tables, columns, types, source systems, schemas            │
│  API: POST /onetb/api/v1/rosetta/pdm/upload                                  │
│                                                                              │
│          │                                                                   │
│          ▼                                                                   │
│                                                                              │
│  PHASE 4: DQ RULE CREATION                                                   │
│  ─────────────────────────────────────────────────────────────────────────   │
│  Who: DQ Analyst / Data Steward (guided by Data Modeller's definitions)      │
│  What: Create DQ rules based on the attribute definitions from LDM/PDM       │
│  Tool: DQMA → DQ Rules module                                                │
│  Output: Named DQ rules with categories (Completeness, Validity, etc.)       │
│  API: POST /dqma/api/cderule (or internal: /onetb/api/v1/dqma/web/cde-rules/save)│
│                                                                              │
│          │                                                                   │
│          ▼                                                                   │
│                                                                              │
│  PHASE 5: RULE LINKAGE                                                       │
│  ─────────────────────────────────────────────────────────────────────────   │
│  Who: Data Steward + Data Modeller (to validate the attribute reference)     │
│  What: Link each DQ rule to its specific PDM column                          │
│  Tool: DQMA → Linkage module                                                 │
│  Output: Linkage records (DRAFT → Review → ReadyForRelease → Live)           │
│  API: PUT /dqma/api/cderulemapping                                           │
│                                                                              │
│          │                                                                   │
│          ▼                                                                   │
│                                                                              │
│  PHASE 6: MONITORING                                                         │
│  ─────────────────────────────────────────────────────────────────────────   │
│  Who: Data Steward + Operations                                               │
│  What: Nightly batch runs all LIVE-linked rules against real data            │
│  Tool: DQMA → Monitor module                                                 │
│  Output: Pass/Fail/Warn results per attribute                                │
│  API: POST /dqma/api/dq-monitor/dashboard-details-by-page                   │
│                                                                              │
│          │                                                                   │
│          ▼                                                                   │
│                                                                              │
│  PHASE 7: EXCEPTION MANAGEMENT                                               │
│  ─────────────────────────────────────────────────────────────────────────   │
│  Who: Data Steward + Source System Owner                                     │
│  What: Raise exceptions for failing attributes, track to resolution          │
│  Tool: DQMA → Exception Workflow module                                      │
│  RAG Status: 🟢 Green (>95%) | 🟡 Amber (80–95%) | 🔴 Red (<80%)            │
│  API: POST /dqma/api/exception-workflow/raise-exception                      │
│                                                                              │
│          │                                                                   │
│          ▼                                                                   │
│                                                                              │
│  PHASE 8: MODEL UPDATE (if needed)                                           │
│  ─────────────────────────────────────────────────────────────────────────   │
│  Who: Data Modeller                                                           │
│  What: Update LDM/PDM if the investigation reveals model inaccuracies        │
│  The change log in Rosetta tracks every modification                         │
│  API: POST /onetb/api/v1/rosetta/ldm/upload (new version)                    │
│                                                                              │
└──────────────────────────────────────────────────────────────────────────────┘
```

---

## 10. Code Snippets — What the Backend Looks Like

### 10.1 How the LDM Service Resolves Attribute Details

The `LdmServiceImpl` in `rosetta-web-service` shows how a data modeller's uploaded attribute data is stored and retrieved:

```java
// LdmServiceImpl.java — searchEntityBy()
// Translates frontend filter names to DB column names:
private static final Map<String, String> FILTER_MAP = Map.of(
    "dataModelKey",   "ldm_model_key",
    "dataModelName",  "ldm_model_name",
    "businessDomain", "ldm_business_domain",   // The domain classification
    "entityName",     "ldm_entity_name",        // The logical entity
    "attributeName",  "ldm_attr_name"           // The attribute
);

// Result type — what the data modeller sees in the UI:
// VLdmBaseinfoDto {
//   ldmModelKey:         "LDM-001",
//   ldmModelName:        "Customer Domain LDM",
//   ldmEntityName:       "Customer",              ← Data modeller defined this
//   ldmAttrName:         "Customer ID",           ← Data modeller defined this
//   ldmAttrDefinition:   "Unique identifier...",  ← Data modeller wrote this
//   ldmAttrDataType:     "STRING",                ← Data modeller specified this
//   ldmAttrNullable:     "N",                     ← Data modeller decided this
//   ldmAttrIsPrimaryKey: "Y"                      ← Data modeller flagged this
// }
```

### 10.2 The Rosetta Graph Builder — Visualising the Data Modeller's Work

The following shows how the LDM graph (ER diagram) is built from data modeller-provided data:

```java
// LdmGraphAdapter.java — building an ER diagram from flat DB rows

// Entity node (the data modeller's entity):
Node entityNode = createGraphNode(
    "2" + entityId,                          // prefix "2" = LogicalEntity
    "LogicalEntity",
    Map.of("name", "Customer"),              // ← Data modeller named this
    true
);

// Attribute nodes (the data modeller's attributes):
Node attrNode = createGraphNode(
    "3" + attrId,                            // prefix "3" = LogicalAttribute
    "LogicalAttribute",
    Map.of("name", "Customer ID",            // ← Data modeller named this
           "dataType", "STRING",             // ← Data modeller typed this
           "isPrimaryKey", "Y"),             // ← Data modeller flagged this
    false
);

// Relationship (the data modeller's cardinality):
Relationship rel = createGraphRelationship(
    "RELATION_TO",
    "2187",   // startNodeId = Customer entity
    "2190",   // endNodeId   = Account entity
    Map.of(
        "relationships", List.of(
            Map.of(
                "key", "FK#ACCT",
                "cardinalityAB", "One and only one",   // ← Data modeller defined
                "cardinalityBA", "Zero or more"         // ← Data modeller defined
            )
        )
    )
);
```

### 10.3 DQMA Linkage — Referencing the Data Modeller's PDM

```java
// LinkageServiceImpl.java — how a linkage references the PDM

// A DQ Analyst creates this linkage record after the Data Modeller
// has uploaded the PDM for the source system:
DqmaRuleLinkageDto linkage = new DqmaRuleLinkageDto();
linkage.setSourceSystem("CORE_BANKING");           // From data modeller's PDM
linkage.setDataDomain("Customer");                 // From data modeller's LDM domain
linkage.setLogicalEntity("Customer Master");       // From data modeller's LDM entity
linkage.setLogicalAttribute("Customer ID");        // From data modeller's LDM attribute
linkage.setPhysicalTable("CUST_MASTER");           // From data modeller's PDM table
linkage.setPhysicalColumn("CUST_SK");              // From data modeller's PDM column
linkage.setRuleId(42L);                            // The DQ Rule to apply
linkage.setStatus(LinkageStatus.REVIEW.getValue());

// Without accurate PDM from the data modeller,
// this linkage would target the WRONG column
// and the entire DQ check would be meaningless.
```

### 10.4 LDM Additional Info — DQ Rules Linked to an Attribute

When a user clicks on an LDM attribute in Rosetta, the `additionalInfo` endpoint returns the DQ rules linked to it. This is the **bridge point** between Rosetta and DQMA:

```typescript
// What the frontend sees when a user clicks on an LDM attribute:
// POST /onetb/api/v1/rosetta/ldm/attribute/additionalInfo
// Response:
{
  "dataModelKey": "LDM-001",
  "entityName": "Customer",
  "attributeName": "Customer ID",
  "dqRules": [
    {
      "ruleName":     "CustomerID_NotNull",
      "ruleCategory": "Completeness",
      "liveStatus":   "Live",            // ← linked via DQMA Linkage
      "lastCheckDate": "2026-06-29",
      "passRate":      99.87             // ← from DQMA Monitor
    },
    {
      "ruleName":     "CustomerID_Format",
      "ruleCategory": "Validity",
      "liveStatus":   "Live",
      "lastCheckDate": "2026-06-29",
      "passRate":      100.00
    }
  ],
  "physicalMappings": [
    {
      "physicalTable":  "CUST_MASTER",   // ← from Data Modeller's PDM
      "physicalColumn": "CUST_SK",
      "databaseType":   "Oracle",
      "sourceSystem":   "CORE_BANKING"
    }
  ]
}
```

### 10.5 DQ Rule Definition — Built on Data Modeller Specifications

```typescript
// A DQ Rule as it exists in the DQMA system.
// The 'ruleBindFields' are populated based on what the Data Modeller
// documented in the LDM/PDM:

const customerIdNotNullRule: Rule = {
  cdeRuleId:           101,
  cdeRuleName:         "CustomerID_NotNull",
  cdeRuleCategory:     "Completeness",      // ← Category matches LDM nullable=false
  cdeRuleTemplateName: "Not Null Check",    // ← Template applied
  cdeRuleDescription:  "Customer ID (CUST_SK) must not be null. Per LDM v3.2: attribute is mandatory.",
  ruleBindFields:      "CUST_SK",           // ← PDM column name from Data Modeller's model
  errorType:           "Hard Check",        // ← CDE = Hard Check (stops pipelines)
  isActive:            "Y",
};

const customerIdFormatRule: Rule = {
  cdeRuleId:           102,
  cdeRuleName:         "CustomerID_Format",
  cdeRuleCategory:     "Validity",          // ← Category matches LDM format constraint
  cdeRuleTemplateName: "Regex Check",
  cdeRuleDescription:  "Customer ID must be alphanumeric, max 20 chars. Per LDM v3.2.",
  ruleBindFields:      "CUST_SK",
  rePattern:           "^[A-Z0-9]{1,20}$",  // ← Based on data modeller's VARCHAR(20) def
  errorType:           "Soft Check",
  isActive:            "Y",
};
```

### 10.6 Transformation Model — Tracking Data Lineage

```typescript
// Transformation record — the data modeller shows exactly how data flows:
const transformation = {
  transformationId:           "TXN-001",
  sourceBusinessDomain:       "Source Systems",
  sourcePhysicalModelKey:     "PDM-SRC-CORE",
  sourcePhysicalTableName:    "RAW_CUSTOMER",       // Source table
  sourcePhysicalColumnName:   "CUSTOMER_ID",        // Source column
  targetBusinessDomain:       "Customer",
  targetPhysicalModelKey:     "PDM-ADS",
  targetPhysicalTableName:    "CUST_MASTER",         // Target table
  targetPhysicalColumnName:   "CUST_SK",             // Target column
  derivationType:             "Direct Copy",          // How the data is mapped
  formula:                    null,                   // Null = no transformation formula
  filterCondition:            "WHERE STATUS = 'ACTIVE'", // Optional filter
  description:                "Active customer IDs copied directly from source"
};
```

---

## 11. Tools, Skills & Techniques

### 11.1 Core Technical Skills

```
MODELLING TOOLS
───────────────────────────────────────────────────────────────
ER/Studio               Industry-standard ER modelling tool
erwin Data Modeler      Enterprise data modelling and metadata
IBM InfoSphere DM       IBM's enterprise modelling platform
Lucidchart / draw.io    Browser-based diagram tools (quick CDMs)
Microsoft Visio         Diagram creation (basic CDMs/LDMs)
Excel                   OneTB uses Excel templates for model input

DATABASE KNOWLEDGE
───────────────────────────────────────────────────────────────
SQL                     Writing queries to validate/explore data
Oracle / PostgreSQL     Understanding physical type constraints
Teradata / Hive         Analytical platform-specific modelling
Data Vault              Modelling approach for audit/historisation
Star/Snowflake Schema   Dimensional modelling for analytics

GOVERNANCE CONCEPTS
───────────────────────────────────────────────────────────────
BCBS 239                Basel Committee data risk management standards
GDPR / PDPA             Data privacy regulations affecting model design
Data Dictionary         Maintaining attribute definitions
Master Data Management  Ensuring single authoritative source per entity
Data Lineage            Tracking data from source to target
Metadata Management     Managing data about data (Rosetta = OneTB's tool)
```

### 11.2 Soft Skills That Matter

| Skill                         | Why It Matters in OneTB                                            |
| ----------------------------- | ------------------------------------------------------------------ |
| **Communication**       | Must translate between business and technical stakeholders         |
| **Attention to detail** | One wrong nullability flag breaks a DQ rule                        |
| **Conflict resolution** | Different teams claim different ownership of the same concept      |
| **Governance mindset**  | Models must go through approval; shortcuts cause downstream issues |
| **Documentation**       | Every attribute needs a clear, unambiguous definition              |
| **Critical thinking**   | "Is Account Number*really* unique?" — don't assume, verify      |

### 11.3 Naming Conventions (Critical in Banking)

Naming is one of the most contested areas in data modelling. OneTB follows strict naming:

```
LDM Naming Convention:
───────────────────────
Entity names:   PascalCase, singular form      → "CustomerAccount" not "customer_accounts"
Attribute names: Title Case with spaces        → "Account Open Date" not "acct_open_dt"
Definitions:    Full sentences, business-first  → "The date on which the customer's account was opened"

PDM Naming Convention:
───────────────────────
Table names:    UPPER_SNAKE_CASE, plural        → "CUST_MASTER", "TXN_DETAIL"
Column names:   UPPER_SNAKE_CASE, abbreviated   → "CUST_SK", "TXN_AMT_USD", "DOB_DT"
Surrogate keys: _SK suffix                      → "CUST_SK", "ACCT_SK"
Date columns:   _DT suffix                      → "CREATE_DT", "UPDATE_DT"
Status columns: _STS_CD suffix                  → "KYC_STS_CD", "ACCT_STS_CD"
Amount columns: _AMT_ with currency             → "TXN_AMT_USD", "SETL_AMT_SGD"
```

---

## 12. Key Terminology Glossary

| Term                      | Meaning                                                       | Where in OneTB                               |
| ------------------------- | ------------------------------------------------------------- | -------------------------------------------- |
| **CDE**             | Critical Data Element — a business-critical attribute        | DQMA Linkage →`cdeName`                   |
| **CDM**             | Conceptual Data Model — business-level concepts              | Rosetta`/explore/metadata/conceptualModel` |
| **LDM**             | Logical Data Model — entity-attribute-relationship blueprint | Rosetta`/explore/metadata/logicalModel`    |
| **PDM**             | Physical Data Model — actual DB tables and columns           | Rosetta`/explore/metadata/physicalModel`   |
| **TDM**             | Transformation Data Model — source-to-target mapping         | Rosetta`/explore/metadata/transformation`  |
| **DQ Rule**         | A named check that data must pass                             | DQMA`/manage/dqma/rule`                    |
| **Linkage**         | Connection between a DQ Rule and a physical attribute         | DQMA`/manage/dqma/linkage`                 |
| **RAG Status**      | Red/Amber/Green severity indicator for DQ scores              | DQMA Exception Workflow                      |
| **4-eye principle** | A different person must approve what you create               | Rosetta and DQMA approval flows              |
| **Cardinality**     | The count relationship between entities (1:1, 1:N, N:M)       | LDM relationships in Rosetta                 |
| **Derivation Type** | How a target column is computed from source                   | TDM in Rosetta                               |
| **Subject Area**    | Top-level grouping in CDM (e.g., "Transactional Banking")     | CDM browse in Rosetta                        |
| **Business Domain** | Domain in LDM/PDM (e.g., "Customer", "Trade")                 | DQMA Monitor filters                         |
| **Surrogate Key**   | System-generated identifier (not from the source)             | PDM column naming (`_SK`)                  |
| **Lineage Graph**   | Visual map of data flow from source to target                 | Rosetta lineage module                       |
| **RTDS**            | Real-Time Data Service — monitors live data pipelines        | OneTB Ingestion module                       |
| **EOD**             | End of Day — when batch DQ checks run                        | DQMA Tech Monitor                            |

---

## 13. Common Anti-Patterns & What Data Modellers Prevent

These are real problems that occur in banks **without** proper data modelling:

```
ANTI-PATTERN 1: The "Catch-All" Table
──────────────────────────────────────────────────────────────────────
Problem:  A developer creates a table with 200 nullable columns because
          "we might need them later." Nobody documents what any of them mean.
Result:   DQ rules cannot be written. Lineage is impossible. Regulatory
          questions cannot be answered.
Data Modeller Fix: Normalise the table. Document every column in PDM.
                   Define which are mandatory.

ANTI-PATTERN 2: Name Collision (The "Customer ID" Problem)
──────────────────────────────────────────────────────────────────────
Problem:  System A uses CUSTOMER_ID as a 10-digit number.
          System B uses CUSTOMER_ID as a 36-char UUID.
          System C uses CUSTOMER_ID as a legacy 6-digit code.
          They are all different things with the same name.
Result:   Joins produce garbage data. DQ checks flag everything as failing.
          Regulatory reports are inconsistent.
Data Modeller Fix: CDM defines ONE "Customer" concept. LDM gives each system
                   its own distinct attribute name with a canonical mapping.

ANTI-PATTERN 3: Missing Lineage
──────────────────────────────────────────────────────────────────────
Problem:  A column TXN_AMT_USD exists in the analytics database.
          Nobody knows where it came from or how it was calculated.
          The formula used 3 years ago was wrong — now all historical
          reports are based on incorrect data.
Result:   Audit failure, potential regulatory fine.
Data Modeller Fix: Transformation model documents the source column,
                   the formula, and the derivation type. Lineage graph
                   makes it visible and auditable.

ANTI-PATTERN 4: DQ Rules on the Wrong Column
──────────────────────────────────────────────────────────────────────
Problem:  A DQ analyst links a "Not Null" rule to CUST_ID, but the
          actual authoritative column is CUST_SK. CUST_ID is always
          populated (it's a join key), but CUST_SK (the real surrogate
          key) sometimes has nulls. The DQ check always passes.
          Real data quality issues are invisible.
Data Modeller Fix: Maintain accurate, current PDM. Mark CUST_SK as the
                   canonical identifier in the LDM. The DQ linkage
                   then correctly targets CUST_SK.

ANTI-PATTERN 5: Stale Models
──────────────────────────────────────────────────────────────────────
Problem:  A new column is added to a source table. The PDM in Rosetta
          is never updated. A year later, nobody knows what the new
          column means or whether DQ rules should apply to it.
Result:   Data gaps in analytics. Ungoverned data in production.
Data Modeller Fix: Every schema change triggers a PDM update in Rosetta.
                   The change log tracks the history. DQ rules are
                   added for the new column within the sprint.
```

---

## 14. Career Growth Path

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    DATA MODELLER CAREER LADDER                              │
│                                                                             │
│  JUNIOR DATA MODELLER                                                       │
│  ─────────────────────────────────────────────────────────────────────      │
│  • Maintain existing CDM/LDM/PDM entries in OneTB Rosetta                  │
│  • Write attribute definitions for new columns                              │
│  • Assist with DQ linkage creation                                          │
│  • Handle model update requests from dev teams                              │
│  • Skills: SQL, Excel, basic ER modelling, business writing                │
│                                                                             │
│          ↓ (2–3 years)                                                     │
│                                                                             │
│  DATA MODELLER                                                              │
│  ─────────────────────────────────────────────────────────────────────      │
│  • Own one or more business domains end-to-end                              │
│  • Design LDM from scratch for new source system onboarding                │
│  • Define CDEs and drive DQ rule creation with DQ team                     │
│  • Create Transformation models for ETL documentation                      │
│  • Skills: ER/Studio or erwin, dimensional modelling, data vault basics    │
│                                                                             │
│          ↓ (3–5 years)                                                     │
│                                                                             │
│  SENIOR DATA MODELLER / LEAD                                                │
│  ─────────────────────────────────────────────────────────────────────      │
│  • Set naming standards, modelling conventions, enterprise glossary         │
│  • Approve junior/mid-level model submissions                               │
│  • Drive the CDM architecture across business domains                      │
│  • Engage regulators on data definitions                                    │
│  • Guide the DQ framework strategy                                          │
│  • Skills: Enterprise architecture, BCBS 239, GDPR, MDM, governance        │
│                                                                             │
│          ↓ (2–4 years)                                                     │
│                                                                             │
│  DATA ARCHITECT / CHIEF DATA OFFICER TRACK                                  │
│  ─────────────────────────────────────────────────────────────────────      │
│  • Define the enterprise data strategy                                      │
│  • Govern the OneTB Rosetta roadmap                                         │
│  • Evaluate and select metadata management tooling                          │
│  • Represent data at the executive level                                    │
│  • Skills: Enterprise architecture, business leadership, regulatory affairs │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## Summary — Data Modellers and OneTB at a Glance

```
┌──────────────────────────────────────────────────────────────────────────────┐
│  WHAT DATA MODELLERS BUILD         │  WHAT IT POWERS IN ONETB               │
│  ──────────────────────────────────┼────────────────────────────────────     │
│  CDM (Subject areas + concepts)    │  Rosetta CDM browse + ER visualisation  │
│  LDM (Entities + attributes)       │  Rosetta LDM browse + attribute detail  │
│  PDM (Tables + columns)            │  Rosetta PDM browse + DQ linkage source │
│  TDM (Source→Target mappings)      │  Rosetta lineage graph (7-day Redis cache)│
│  CDE identification                │  DQMA DQ Rule creation target           │
│  Attribute definitions             │  DQMA rule category selection           │
│  Domain/subdomain classification   │  DQMA Monitor filter groupings          │
│  Nullable/format constraints       │  DQMA Completeness + Validity rules     │
│  Source system identification      │  DQMA Linkage source system field       │
│  Transformation documentation      │  RTDS channel config validation         │
│  Change log maintenance            │  Rosetta audit trail per attribute      │
│  4-eye approval of their own models│  Rosetta upload governance workflow     │
└──────────────────────────────────────────────────────────────────────────────┘
```

> **Final thought:** A data modeller in OneTB is not just someone who draws boxes and arrows. They are the **source of truth** for what every column in the bank's data warehouse means, where it comes from, and what rules it must follow. Every DQ check that catches a bad record, every lineage graph that answers a regulator's question, and every monitor alert that catches a pipeline failure — they all trace back to the foundational work of a data modeller.

---

*Document maintained by the OneTB Data Governance team. Last updated: June 2026.*
*For queries, raise a ticket via the OneTB Action Centre or contact the Rosetta team.*
