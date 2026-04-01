---
trigger: always_on
---

# Documentation Naming Conventions & Structure
 
## 1. General Principles
To maintain a searchable and scalable documentation system, all contributors must follow these naming rules:

* **Characters:** Use only alphanumeric characters (`A-Z`, `a-z`, `0-9`) and underscores (`_`).
* **Separators:** Use underscores (`_`) instead of spaces. Do not use hyphens `-` except for Functional Requirement IDs.
* **Case Style:** Use **PascalCase** for main entity names and **Snake_case** for descriptive attributes.
* **Language:** Documentation must be written in **English** for consistency across the development lifecycle.

---

## 2. Directory-Specific Naming Rules

### 📂 00_Overview & 01_Business
Focuses on high-level strategy and master logs.
* **Format:** `[Document_Name].md`
* **Examples:** `Vision_and_Scope.md`, `Business_Rules_Log.md`, `Glossary.md`.

### 📂 02_Product (Feature-level)
Links business requirements to technical implementation.
* **Format:** `[Module_Code]-[Sub_Module]-[ID]_[Feature_Name].md`
    * `Module_Code`: Typically `FR` (Functional Requirement).
    * `Sub_Module`: Category identifier (A, B, C...).
    * `ID`: Sequential number (01, 02...).
* **Example:** `FR-A-01_User_Management.md`, `FR-B-05_Payment_Integration.md`.

### 📂 03_Design
Focuses on visual logic and interface specs.
* **User Flows:** `Flow_[Process_Name].md` (e.g., `Flow_Checkout_Process.md`).
* **Screen Specs:** `Screen_[Persona]_[Screen_Name].md` (e.g., `Screen_Admin_Dashboard.md`).
* **Wireframes:** `Wireframe_[Feature_Name].md`.

### 📂 System
Contains complex backend logic, algorithms, or API mapping.
* **Format:** `Logic_[Module_Name].md`
* **Example:** `Logic_Price_Calculation.md`, `Logic_Data_Sync.md`.

---

## 3. Reference Structure

```text
docs/
├── 00_Overview/
│   ├── 00_Vision_and_Scope.md
│   └── Glossary.md
├── 01_Business/
│   ├── User_Personas.md
│   └── Business_Rules_Log.md
├── 02_Product/
│   ├── features/
│   │   ├── FR-A-01_Identity_Access.md  <-- [Code]-[ID]_[Name]
│   │   └── FR-B-01_Inventory_Search.md
│   └── Acceptance_Criteria.md
├── 03_Design/
│   ├── User_Flows/
│   │   └── Flow_Onboarding.md          <-- Flow_ prefix
│   ├── Screen_Specs/
│   │   └── Screen_Tutor_Profile.md     <-- Screen_ prefix
│   └── Wireframes/
├── System/
│   └── Logic_Auth_Token_Workflow.md    <-- Logic_ prefix
└── Templates/
    └── PRD_Template.md