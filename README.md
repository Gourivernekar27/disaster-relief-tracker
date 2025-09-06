# 🌍 Disaster Relief Management System — SQL + DBMS Project

> 🚨 Built to Extract Critical Insights During Crisis Situations Using Relational Databases and SQL Analytics

This project models a realistic **Disaster Relief Management System** that captures the coordination between relief zones, government agencies, NGOs, and deployed resources during natural calamities. It was designed to extract **meaningful insights** using SQL queries — from identifying under-served zones and delayed deployments, to assessing the scale of damage and response patterns across states.

📌 Whether it’s a flood, earthquake, or cyclone — this project simulates how data can be stored, queried, and analyzed to **support real-time decisions** during emergencies.

---

## 📊 Project Objectives

- Track resources and deployments across relief zones.
- Measure NGO/agency responsiveness and resource utilization.
- Visualize impact severity across zones and time.
- Derive actionable insights to optimize future relief efforts.

---

## 🛠️ Technologies Used

- **Database:** PostgreSQL / MySQL (interchangeable)
- **SQL Concepts:** Joins, Views, Aggregations, Triggers, Window Functions, Subqueries, Date functions
- **Documentation:** GitHub markdown + PNG screenshots + CSV exports

---

## 🧾 Dataset Description

The dataset was **custom-generated** to simulate real-world scenarios, taking inspiration from verified sources such as:
- [ReliefWeb](https://reliefweb.int/)
- [NDMA India](https://ndma.gov.in/)
- Government & NGO data repositories

While not taken from a specific site, the dataset structure and field types closely follow actual disaster response patterns and documentation standards. It was generated entirely by me for **academic and study purposes**, enabling controlled experimentation and insight extraction.

---

## 🧩 Schema Overview

The database consists of **5 relational tables**:

### 1. `relief_zones`
| Attribute       | Type        | Description                              |
|----------------|-------------|------------------------------------------|
| `zone_id`      | INTEGER (PK)| Unique zone identifier                   |
| `zone_name`    | TEXT        | Name of the affected area                |
| `state`        | TEXT        | Indian state the zone belongs to         |
| `disaster_type`| TEXT        | Type of disaster (e.g., Flood, Earthquake)|
| `date_declared`| DATE        | Date when the zone was declared in crisis|

### 2. `agencies`
| Attribute         | Type        | Description                            |
|------------------|-------------|----------------------------------------|
| `agency_id`       | INTEGER (PK)| Unique agency identifier               |
| `agency_name`     | TEXT        | Name of the NGO or government body     |
| `contact_person`  | TEXT        | Person in charge                       |
| `phone`           | TEXT        | Contact number                         |
| `email`           | TEXT        | Official contact email                 |

### 3. `resources`
| Attribute      | Type        | Description                                |
|---------------|-------------|--------------------------------------------|
| `resource_id` | INTEGER (PK)| Unique ID for each resource                |
| `resource_type`| TEXT        | e.g., Food, Medical Kit, Tent              |
| `quantity`    | INTEGER     | Number of units available                  |
| `unit`        | TEXT        | Measurement unit (kg, boxes, kits, etc.)   |
| `zone_id`     | INTEGER (FK)| Zone where the resource is allocated       |

### 4. `deployments`
| Attribute        | Type        | Description                              |
|------------------|-------------|------------------------------------------|
| `deployment_id`  | INTEGER (PK)| Unique deployment record                 |
| `agency_id`      | INTEGER (FK)| Agency conducting the deployment         |
| `resource_id`    | INTEGER (FK)| Resource being deployed                  |
| `zone_id`        | INTEGER (FK)| Zone to which deployment was made        |
| `deployment_date`| DATE        | Date of deployment                       |

### 5. `impact_reports`
| Attribute         | Type        | Description                            |
|-------------------|-------------|----------------------------------------|
| `report_id`       | INTEGER (PK)| Unique impact report identifier        |
| `zone_id`         | INTEGER (FK)| Related zone                           |
| `affected_population` | INTEGER | Number of people affected              |
| `casualties`      | INTEGER     | Number of deaths                       |
| `houses_damaged`  | INTEGER     | Homes damaged or destroyed             |
| `updated_on`      | DATE        | Last updated timestamp                 |

> 🔗 All relationships are enforced via **foreign keys**. The schema was designed to maintain referential integrity and normalize data across core entities (zones, agencies, resources).

---

## 📂 Folder Structure
<pre><code> 📁 disaster-relief-sql-project/ ├── 📁 datasets/ # CSV files for each table │ ├── relief_zones.csv │ ├── agencies.csv │ ├── resources.csv │ ├── deployments.csv │ └── impact_reports.csv │ ├── 📁 queries/ # SQL queries for insight extraction │ └── Disaster Relief SQL Queries.txt # Contains 18 analytical queries │ ├── 📁 query output files/ # CSV results of each query │ ├── query1.csv │ ├── query2.csv │ └── ... │ ├── 📁 query output screenshots/ # PNG screenshots of each query's output │ ├── output1.png │ ├── output2.png │ └── ... │ ├── 📁 schema diagram/ # Entity-Relationship Diagram │ └── ER_diagram.png │ └── README.md # Project overview and documentation </code></pre>
## 📈 Insightful SQL Queries (18+)

Each query is designed to extract real-world insights, including:

1. ✅ **Zones with highest casualties**
2. 🕐 **Average time between disaster and deployment**
3. 🛠️ **Most commonly deployed resource types**
4. 📉 **Under-served zones with high impact but fewer deployments**
5. 📊 **Agency performance across deployments**
6. 📍 **Zone-wise disaster trends**
7. 🧮 **Total aid deployed per state**
8. 🔁 **Trigger-based audits for deployment updates**
9. 🧵 **Window functions for ranking zones**
10. 👥 **Casualty-to-population ratio insights**
11. ⏳ **Delayed deployment tracking**
12. ...and more

Each of these has been documented via:
- CSV Output (`query output files/`)
- Screenshot (`query output screenshots/`)
- SQL Query (`querie/squeries.sql`)

---
## 🔗 Live Dashboard (Tableau)

I also built an **interactive dashboard** to visualize these insights:  

👉 [Click here to view the Disaster Relief Dashboard on Tableau Public](https://public.tableau.com/views/DisasterRelief-Dashboard/Dashboard1)  

📸 Preview:  
![Dashboard Screenshot](dashboard_preview.png)  

## 🔎 Why This Project Matters

Disasters demand **rapid, informed, and data-driven** responses. This project showcases how relational databases, when combined with powerful SQL analytics, can:
- Guide **decision-making** in real time
- Help **allocate resources efficiently**
- Track **NGO accountability and impact**
- Prepare governments for **future crises**

---

## ✅ Project Completion

This project was entirely built, documented, and structured by **Gouri Vernekar** as part of a self-directed effort to master data analysis using DBMS and SQL. It serves as a comprehensive case study to understand how data can drive decisions during critical emergencies — and how well-designed databases and queries can surface that information clearly.
