# 💧 Maji Ndogo: National Water Crisis Analytics

## Project Overview
This repository contains the SQL scripts and analysis for the **Maji Ndogo Water Project**, an end-to-end data analytics initiative aimed at solving a simulated national water crisis. Working with a database of over 60,000 records, the goal was to clean the data, uncover hidden patterns, investigate discrepancies, and ultimately provide actionable insights to deploy engineering teams and fix the country's water infrastructure.

## 🛠️ Tech Stack & Tools
* **Database Management:** MySQL
* **Languages:** SQL (DDL, DML, DQL)
* **Techniques:** Data Cleaning, Aggregations, Window Functions, Table Joins, Subqueries, CTEs, Views, and Database Normalization.

## 📂 Repository Files
* **`md_water_services.sql`**: The foundational data exploration script. This file documents the initial steps taken to understand the raw data structure, beginning with isolating unique records (`SELECT DISTINCT`) in the `water_source` table to identify the various types of water infrastructure across the country.

## 🗄️ Database Architecture
The analysis relies on a highly relational database structure. 
Key tables include:
* `employee`: Details of field workers and engineers.
* `water_source`: Types of sources (taps, wells, rivers, etc.) and their capacities.
* `visits`: Logs of employee visits to water sources, including queue times.
* `well_pollution`: Biological and chemical test results for well water.
* `auditor_report`: Independent findings to verify field worker data.
* `project_progress`: A tracked table built to manage the ongoing repair operations.

## 🔍 The Investigation Phases

### Phase 1: Data Exploration & Cleaning
* **Objective:** Understand the raw survey data and correct initial logging errors.
* **Actions:** Explored tables using basic `SELECT` queries, corrected misspelled email addresses, and used `LIKE` operators and string functions to fix poorly formatted pollution records (e.g., standardizing "Clean Bacteria: E. coli" to "Bacteria: E. coli").

### Phase 2: Deep Dive & Aggregations
* **Objective:** Cluster the data to understand the geographical spread and severity of the crisis.
* **Actions:** Grouped data by province and town to find the hardest-hit areas. Analyzed wait times to discover that citizens were queueing for over 30 minutes on average at shared taps. Formulated initial short-term solutions (e.g., dispatching water tankers during peak times) and long-term goals (e.g., installing reverse osmosis filters for polluted wells).

### Phase 3: Database Relationships & Fraud Investigation
* **Objective:** Stitch the database together and verify data integrity following suspicions of foul play.
* **Actions:** Mapped out the Entity-Relationship Diagram (ERD). Integrated an independent auditor's report using complex `JOIN` operations to compare official records against audit findings. **Outcome:** Uncovered a data falsification ring. Identified four corrupt employees (Zuriel, Malachi, Bello, and Lalitha) who were logging broken wells as functional in exchange for bribes.

### Phase 4: Actionable Planning & Views
* **Objective:** Transform analytical insights into a practical engineering roadmap.
* **Actions:** Built complex queries utilizing Common Table Expressions (CTEs) and Window Functions to consolidate the final dataset. Created a `project_progress` table to track the repair of broken infrastructure, assigning specific intervention types (e.g., "Install UV filter", "Drill new well") to individual locations. 

## 🚀 Key Outcomes
1. **Identified the Core Bottlenecks:** Pinpointed specific regions suffering from extreme queue times and broken shared taps.
2. **Exposed Corruption:** Successfully flagged corrupt field workers, allowing leadership to take immediate action and restore data integrity.
3. **Deployed Solutions:** Generated a comprehensive, actionable project tracking table that guides engineering teams on exactly what to fix, where, and how.

## Acknowledgments
A massive thank you to **ALX Ghana** for curating the Data Analytics program that provided the foundational skills and rigorous training needed to execute this project.
