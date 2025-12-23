🚨 AI Incident Commander
AI Incident Commander is a serverless disaster-response decision support system that analyses incident data and identifies which disaster requires immediate attention. It helps emergency control rooms reduce response time and prioritise actions using data-driven intelligence.

🧠 Problem Statement
During disasters, control rooms receive large volumes of incident data from multiple sources. Manual analysis causes delays, confusion, and inefficient resource allocation.

✅ Solution
>>AI Incident Commander automatically
>>Cleans incoming disaster data
>>Analyses key risk factors
>>Ranks incidents by urgency
>>Highlights the most critical incident first

🏗️ System Architecture
Frontend: Web dashboard for upload & visualisation
AWS S3: Stores raw and processed CSV/JSON files
AWS Lambda: Cleans data and calculates priority scores
API Gateway: Connects frontend and backend

🔄 Workflow

--> User uploads CSV/JSON incident data
--> File is stored in AWS S3
--> S3 triggers a Lambda function
--> Lambda cleans and analyses the data
-->Priority scores are generated
-->Incidents are ranked by urgency
-->Results are sent to the frontend

📊 Priority Logic

Each incident is evaluated using:
Severity level
Number of people affected
Response delay

A priority score is calculated and incidents are sorted from highest to lowest urgency.

🧪 Sample Input
incident_id,incident_type,severity,people_affected,response_time
101,Flood,5,1200,45
102,Fire,3,200,10
103,Cyclone Alert,4,5000,120

📤 Output
>>Ranked list of incidents
>>Highlighted most critical disaster
>>Cleaned and processed data stored in S3

🚀 Tech Stack

AWS S3
AWS Lambda (Python)
AWS API Gateway
HTML / CSS / JavaScript

🌍 Use Cases

Disaster management control rooms
Smart city emergency response
Flood, fire, cyclone monitoring systems
