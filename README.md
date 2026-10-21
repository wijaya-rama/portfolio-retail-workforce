# Retail Workforce Productivity & Attrition Analysis

[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Live%20Demo-2563EB?style=for-the-badge&logo=github)](https://wijaya-rama.github.io/portfolio-retail-workforce/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)
[![Vanilla JS](https://img.shields.io/badge/Vanilla_JS-ES6+-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Data Architecture](https://img.shields.io/badge/Data-Star_Schema_&_Flat_CSV-10B981?style=for-the-badge&logo=microsoftexcel&logoColor=white)](data/)

> Interactive People Analytics & Workforce Productivity Dashboard evaluating employee turnover dynamics, leadership styles, labor cost structures, and high-performer retention across **2,000 retail employees** and **24 stores** over 2024–2025.

[Launch Interactive Dashboard (Live Demo)](https://wijaya-rama.github.io/portfolio-retail-workforce/)

---

## Executive Summary

In high-volume retail operations, frontline employee turnover and escalating labor cost percentages directly erode store-level EBITDA and customer experience. This study executes an empirical People Analytics investigation across 24 stores in 3 operational regions (*Midwest*, *South*, *West*), tracking 2,000 personnel over a 24-month longitudinal timeline (January 2024 – December 2025).

Designed around a **Takeaway-First Storytelling** methodology and a responsive **Bento Grid Architecture**, the dashboard provides actionable business intelligence for Chief Human Resources Officers (CHRO), Retail Operations Directors, and Regional General Managers.

---

## Key Business Insights

```
+---------------------------------------------------------------------------------------+
|                                    CORE TAKEAWAYS                                     |
+--------------------------+--------------------------+---------------------------------+
|   Micromanagement Risk   |   Store Inefficiencies   |      Star Talent Attrition      |
|          48.8%           |      Express Stores      |              20.7%              |
|  Team attrition rate     |   Highest labor cost %   |   1 in ~5 top performers quit   |
|  under micromanagers     |   Bottom revenue/emp.    |   (Not driven by compensation)  |
+--------------------------+--------------------------+---------------------------------+
```

### 1. Leadership Style Drives Retention: Micromanagement vs. Attrition (48.8%)
* Teams supervised by managers exhibiting a **Micromanagement** archetype suffered an aggregate attrition rate of **48.8%**, compared to **12%–14%** under **Coaching** and **Standard** managers.
* Micromanaging supervisors accounted for a disproportionate share of all voluntary exits. Scatter regression confirms a steep negative correlation between a manager's leadership score and their team's annualized turnover rate.

### 2. Operational Inefficiency in Express Store Formats
* **Express format stores** consumed a significantly larger share of top-line revenue on labor costs relative to **Regular** and **Superstore** formats.
* Across all three operational regions, Express stores consistently clustered at the bottom of **Revenue per Employee (RPE)** metrics, exposing rigid shift scheduling and low sales productivity during off-peak hours.

### 3. High-Performer Vulnerability: 20.7% Star Talent Attrition (9-Box Grid)
* Analysis across the **9-Box Performance vs. Potential Matrix** revealed an acute retention vulnerability: **20.7% (approximately 1 in 5) of categorized Star Talents resigned**.
* Compensation was **not** the primary exit trigger: the average *compa-ratio* of departed talent (**0.98**) was virtually identical to those who stayed (**0.99**). Exit interview data confirms that managerial friction, lack of autonomy, and stagnant progression prompted top talent to leave.

### 4. Critical Tenure Window: First-Year Vulnerability (< 1 Year)
* Turnover risk peaked sharply within the first 12 months of employment. New hires (< 1 year tenure) experienced significantly higher dropout rates than tenured staff (3+ years), highlighting an operational onboarding gap.

---

## Strategic Management Recommendations

| Strategic Pillar | Target Metric | Recommended Operational Intervention |
| :--- | :--- | :--- |
| **1. Leadership Transformation** | Reduce team turnover to < 20% | Implement managerial coaching academies; restructure or reassign teams under persistent micromanagers before escalating payroll budgets. |
| **2. New-Hire Shielding** | Decrease 1st-year attrition by 30% | Establish structured peer mentorship with mandatory check-ins at Month 3 and Month 6. |
| **3. Star Talent Retention Protocol** | Retain >= 90% of 9-box top performers | Deploy Individual Development Plans (IDP), priority project rotations, and quarterly skip-level executive dialogues. |
| **4. Express Store Optimization** | Lower Express labor cost by 2.5 pts | Introduce dynamic demand-based shift scheduling aligned with hourly footfall patterns. |

---

## System Architecture & Data Model

```mermaid
flowchart LR
    A["Raw Retail Dataset<br/>(2,000 Employees)"] --> B["Dimensional Modeling<br/>(Fact & Dim Tables)"]
    B --> C["Star Schema Excel<br/>& Flat CSV Exports"]
    C --> D["Lightweight Frontend<br/>(Vanilla JS ES6+ & SVG)"]
    D --> E["Bento Grid Dashboard<br/>(GitHub Pages)"]
```

### 1. Data Modeling & Storage (`data/`)
* **`Retail_Workforce_Productivity_StarSchema.xlsx`:** Relational dimensional star schema consisting of:
  * **Fact Table:** `Fact_Monthly_Productivity` (monthly store revenue, labor cost, headcounts, CSAT scores).
  * **Dimension Tables:** `Dim_Employee`, `Dim_Store`, `Dim_Manager`, and `Dim_Date`.
* **`Retail_Workforce_Productivity_Flat_2000.csv`:** Denormalized master record containing granular employee profiles (demographics, 9-box categorization, compa-ratio, tenure, flight risk, exit reasons, and operational KPIs).

### 2. Frontend Engineering & Visual Design
* **Zero External Dependencies:** Built entirely with semantic HTML5 and vanilla JavaScript (ES6+) — zero npm packages, build steps, or bundle overhead.
* **Native Scalable Vector Graphics (SVG):** Custom dynamic bar charts, sparklines, and scatter plots rendered directly to the DOM for 60fps responsiveness and sub-100ms load times.
* **Bento Grid Layout:** High data-ink ratio, WCAG-compliant contrast ratios, integrated dark/light theme persistence, and an instant **Bilingual Toggle (EN / ID)**.

---

## Repository Structure

```text
portfolio-retail-workforce/
├── index.html       # Production-ready interactive dashboard (GitHub Pages entry point)
├── .gitignore       # Git exclusion rules for OS, IDE, and temporary files
├── README.md        # Executive portfolio documentation & business insights
├── LICENSE          # MIT open-source license
└── data/            # Source data assets
    ├── Retail_Workforce_Productivity_Flat_2000.csv       # Denormalized master CSV (2,000 rows)
    └── Retail_Workforce_Productivity_StarSchema.xlsx      # Relational dimensional model
```

---

## Deployment & Execution Guide

### Option 1: Direct Local Execution (Instant)
Because the application is fully self-contained with no runtime dependencies:
1. Clone the repository:
   ```bash
   git clone https://github.com/wijaya-rama/portfolio-retail-workforce.git
   cd portfolio-retail-workforce
   ```
2. Open [`index.html`](index.html) directly in any modern web browser (Google Chrome, Microsoft Edge, Mozilla Firefox, Safari).

### Option 2: Local HTTP Server
* **Using Python 3:**
  ```bash
  python -m http.server 8000
  ```
  Navigate to `http://localhost:8000`.
* **Using Node.js (npx):**
  ```bash
  npx serve .
  ```
* **Using VS Code:**
  Right-click `index.html` and select **Open with Live Server**.

### Option 3: GitHub Pages Deployment
1. Push this repository to GitHub.
2. Navigate to **Settings** > **Pages**.
3. Under **Build and deployment** > **Source**, choose **Deploy from a branch**.
4. Set the branch to `main` and folder to `/ (root)`, then click **Save**.
5. The live dashboard is accessible at:
   `https://wijaya-rama.github.io/portfolio-retail-workforce/`

---

## Author & Contact

**Rama Wijaya**  
*Data Analyst | Livestock Enthusiast & Business Intelligence*

* **LinkedIn:** [linkedin.com/in/ramawijaya1](https://www.linkedin.com/in/ramawijaya1)
* **GitHub:** [@wijaya-rama](https://github.com/wijaya-rama)
* **Portfolio Repository:** [portfolio-retail-workforce](https://github.com/wijaya-rama/portfolio-retail-workforce)
* **Interactive Live Demo:** [wijaya-rama.github.io/portfolio-retail-workforce](https://wijaya-rama.github.io/portfolio-retail-workforce/)

---

## License

This project is licensed under the [MIT License](LICENSE) — feel free to adapt and reference this project for analytics benchmarking and portfolio development.
