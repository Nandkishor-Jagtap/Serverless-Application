📚 AWS Serverless Student Management System

A fully serverless web application built using AWS services to store and retrieve student data without managing any servers.

This project demonstrates:

Serverless backend using Lambda + API Gateway

DynamoDB for NoSQL data storage

S3 + CloudFront for hosting the web application

CORS configuration

Secure access using IAM roles and policies

---

✅ 1️⃣ Project Architecture

📷 Architecture Diagram:
![Architecture](Project-Documents/architecture.jpg)

Frontend

HTML, CSS, JavaScript hosted in S3

AJAX calls to API Gateway

Backend

AWS API Gateway (GET & POST endpoints)

AWS Lambda functions

AWS DynamoDB table

Delivery

AWS CloudFront CDN to access the website globally

---

✅ 2️⃣ Services Used
Service	Purpose
DynamoDB	Stores student records
Lambda (2 functions)	insertStudentData & getStudents
API Gateway	Exposes REST API (GET & POST)
IAM Roles	Secure Lambda access to DynamoDB
S3 Bucket	Hosts static frontend website
CloudFront	Serves website globally & securely
CloudWatch	Logs and debugging

📷 DynamoDB Screenshot:
![DynamoDB](Project-Documents/dynamodb.jpg)

📷 Lambda Screenshot:
![Lambda](Project-Documents/lambda.jpg)

📷 API Gateway Screenshot:
![API](Project-Documents/api.jpg)

📷 S3 Hosting Screenshot:
![S3](Project-Documents/s3.jpg)

📷 CloudFront Screenshot:
![CloudFront](Project-Documents/cloudfront.jpg)

📷 UI Screenshot:
![UI](Project-Documents/UI.jpg)

--

✅ 3️⃣ Steps Performed
✅ Step 1: Create DynamoDB Table

Table Name: student

Partition Key: studentid (String)

📷 Project Documents/dynamodb.jpg

✅ Step 2: Create Lambda Functions

🔹 Function 1: insertStudentData

Accepts POST request

Inserts student data into DynamoDB

🔹 Function 2: getStudents

Accepts GET request

Returns all student records

✅ IAM Permissions Added:

AmazonDynamoDBFullAccess

AWSLambdaBasicExecutionRole

📷 Project Documents/lambda.jpg

✅ Step 3: Create API Gateway

✅ Created a REST API with:

Method	Lambda Integration	Description
POST	insertStudentData	Save student
GET	getStudents	Fetch all students

✅ Enabled CORS for both methods
✅ Deployed API to prod stage
✅ Copied Invoke URL for frontend

📷 Project Documents/api.jpg

✅ Step 4: Frontend Development

Created index.html and scripts.js

Added AJAX calls:

POST → Save student

GET → Retrieve students

Updated API_ENDPOINT with API Gateway URL

📷 Project Documents/UI.jpg

✅ Step 5: Host Website on S3

Created S3 bucket

Enabled Static Website Hosting

Uploaded HTML, JS, CSS files

Updated permissions to allow public access

📷 Project Documents/s3.jpg

✅ Step 6: Fixing CORS Issue

Enabled CORS in API Gateway

Redeployed the API

Tested APIs successfully

📷 Project Documents/api.jpg

✅ Step 7: Add CloudFront (CDN)

Created CloudFront distribution

Origin: S3 bucket

Set Default Root Object: index.html

Applied bucket policy for CloudFront access

Final website accessible via CloudFront URL

📷 Project Documents/cloudfront.jpg

--


✅ 4️⃣ How the App Works

1️⃣ User enters student details on the website
2️⃣ Website calls POST API → Lambda → DynamoDB (data saved)
3️⃣ Clicking "View Students" calls GET API
4️⃣ Lambda returns data → Displayed in table

✅ No servers needed
✅ Fully automated

📷 Project Documents/UI.jpg

--

✅ 5️⃣ Final Output

Static website accessible globally via CloudFront

Insert & View Student Data in real-time

Serverless, scalable, low-cost application

📷 Project Documents/UI.jpg
