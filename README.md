#Project Overview

This repository contains an end-to-end data analytics project focused on optimizing subscriber consumption, understanding viewer behavior, and driving growth for BrightTV.
Using historical datasets containing granular subscriber demographics and transactional viewing records, this project delivers actionable, data-driven insights to assist the Customer Value Management (CVM) team in expanding BrightTV’s subscription base and maximizing platform engagement.


#Business Problem & Objectives

BrightTV’s executive leadership has set a critical objective: scale the platform’s subscriber base this financial year. To do this, the CVM team needs full visibility into the hidden drivers behind user consumption patterns, geographic/demographic preferences, and content performance.
Without deep analytics, the business risks:
• High Customer Churn: Failing to engage "at-risk", low-consumption users before they unsubscribe.
• Misallocated Content Spend: Programming the wrong content mix during peak versus off-peak viewership cycles.
• Inefficient Marketing ROI: Deploying broad subscriber acquisition strategies instead of hyper-targeted, demographic-specific digital campaigns.


#Key Analytical Deliverables:

1. Trend Analysis: Map user and usage trends across months, days of the week, and hours.
2. Consumption Drivers: Isolate demographic, geographic, and temporal factors influencing platform viewing.
3. Low-Consumption Remediation: Recommend specific programming strategies to boost traffic on low-viewership days.
4. Acquisition Strategy: Design tactical initiatives leveraging social media and market segmentation to grow the absolute user base.


#Data Pipeline & Architecture

The project applies a structured ETL (Extract, Transform, Load) pipeline to ingest, clean, and combine disconnected data layers into an executive dashboard asset:
[RAW SOURCE INGESTION]
   - User Profiles: Subscriber Master (ID, Name, Gender, Race, Age, Province, Social Handles)
   - Viewership Transactions: Log Layer (UserID, Channel, UTC Timestamps, Viewing Duration)
            │
            ▼
[ETL & DATA ENGINEERING LAYER]
   - 1. Structural Localisation: Convert timestamp logs from UTC to SA Standard Time (SAST = UTC + 2 Hours)
   - 2. Feature Engineering: Cast text time durations (HH:MM:SS) into absolute numeric viewing minutes
   - 3. Data Cleaning: Clean missing profile values; flag extreme outliers (e.g., Age > 100)
   - 4. Relational Join: Combine master metrics using an INNER JOIN on [UserID]
            │
            ▼
[DIAGNOSTIC & PRESCRIPTIVE REPORTING]
   - Interactive Analytics Model -> CVM Strategic Pitch Deck & Executive Dashboard


#Data Stack & Core Tooling

• SQL / Databricks SQL: Deployed for high-performance data modeling, multi-table relation joins, and structural data validation metrics.
• Microsoft Power BI / Advanced Excel: Utilized to map data schemas, structure data hierarchies, and compile interactive stakeholder dashboards.
• Microsoft PowerPoint: Utilized to compile the final strategic 20-minute presentation tailored specifically for executive leadership and the CEO [INDEX: 0.1.4].
