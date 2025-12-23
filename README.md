# 🚨 AI Incident Commander

**AI Incident Commander** is a **serverless disaster-response decision support system** that analyses incident data and determines **which disaster requires immediate attention**.  
It enables emergency control rooms to **reduce response time**, **avoid confusion**, and **prioritise actions** using data-driven intelligence.

---

## 🧠 Problem Statement

During large-scale disasters, emergency control rooms receive **high volumes of incident data** from multiple sources (CSV / JSON files).

Manual analysis leads to:
- Delayed decision-making  
- Conflicting priorities  
- Inefficient allocation of emergency resources  

There is a need for an **automated system** that can quickly analyse incidents and highlight the **most critical situations first**.

---

## ✅ Solution Overview

**AI Incident Commander** automatically:

- Cleans incoming disaster data  
- Analyses key risk indicators  
- Calculates priority scores  
- Ranks incidents by urgency  
- Highlights the most critical disaster for immediate action  

This allows decision-makers to **focus on what matters most, first**.

---

## 🏗️ System Architecture

**Frontend**
- Web dashboard for data upload and result visualisation  

**Backend (Serverless)**
- **AWS S3** – Stores raw and processed CSV/JSON files  
- **AWS Lambda (Python)** – Cleans data and computes priority scores/db
- **AWS API Gateway** – Connects frontend and backend services  

---

## 🔄 Workflow

1. User uploads CSV/JSON incident data via the web dashboard  
2. File is stored in **AWS S3**  
3. S3 triggers a **Lambda function**  
4. Lambda cleans and analyses the data  
5. Priority scores are generated  
6. Incidents are ranked by urgency  
7. Results are sent back to the frontend for display  

---

## 📊 Priority Logic

Each incident is evaluated using the following parameters:

- **Severity level**
- **Number of people affected**
- **Response delay (in minutes)**

A **priority score** is calculated, and incidents are sorted from **highest to lowest urgency**.

---

## 🧪 Sample Input

```csv
incident_id,incident_type,severity,people_affected,response_time
101,Flood,5,1200,45
102,Fire,3,200,10
103,Cyclone Alert,4,5000,120
