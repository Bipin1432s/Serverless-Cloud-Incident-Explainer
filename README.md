# Serverless Cloud Incident Explainer

A serverless cloud monitoring application that captures, stores, and visualizes cloud incidents using AWS Lambda, API Gateway, DynamoDB, and S3. The system exposes a real-time REST API to fetch incidents and displays them in a web-based dashboard.

---

## Technologies Used

- AWS Lambda  
- API Gateway (HTTP API)  
- DynamoDB  
- Amazon S3 (Static Website Hosting)  
- IAM  
- HTML, CSS, JavaScript  

---

## Architecture

User Browser

↓

S3 Static Website

↓

API Gateway (HTTP API)

↓

AWS Lambda

↓

DynamoDB

---

## Features

- Serverless REST API for retrieving cloud incidents  
- DynamoDB backend for storing incident records  
- Public dashboard to visualize incidents in real-time  
- Built completely on AWS Free Tier compatible services  

---

## Setup Steps

### 1. Create DynamoDB Table
- Table Name: Incident_Events  
- Partition Key: incident_id (String)

---

### 2. Create Lambda Function
- Runtime: Python 3.11  
- Attach policies:
  - AmazonDynamoDBFullAccess  
  - CloudWatchLogsFullAccess  

---

### 3. Create API Gateway
- Create HTTP API  
- Route: GET /incidents  
- Integration: Lambda  
- Payload format version: 2.0  

---

### 4. Configure Permissions
Grant API Gateway permission to invoke Lambda using the execution ARN.

---

### 5. Deploy Frontend
- Upload index.html to S3  
- Enable Static Website Hosting  
- Allow public access via bucket policy  

---

### 6. Access Application
Open the S3 website endpoint and click **Load Incidents** to view live cloud incidents.

---

## Output

The dashboard displays incident ID, service name, severity, root cause, status, and timestamp.

---

## Learning Outcomes

- Built an end-to-end serverless application  
- Integrated AWS Lambda with API Gateway and DynamoDB  
- Implemented real-time data visualization with S3 static hosting  

---

## License

This project is open for learning and portfolio usage.
