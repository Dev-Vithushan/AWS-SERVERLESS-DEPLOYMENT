# Deploying Serverless Web Application on AWS: S3, API Gateway, Lambda, DynamoDB, and CloudFront

This document outlines the steps to deploy a serverless web application on AWS, utilizing a combination of services including Amazon S3, Amazon API Gateway, AWS Lambda, Amazon DynamoDB, and Amazon CloudFront. By using this architecture, you can achieve a highly scalable, cost-efficient solution without the need to manage any servers

### Key AWS Services
- `Amazon S3:` Used to host static assets such as HTML, CSS, JavaScript, and media files.
- `Amazon API Gateway:` Provides a REST API endpoint that acts as a proxy for AWS Lambda functions.
- `AWS Lambda:` Handles backend business logic with scalable, event-driven compute services.
- `Amazon DynamoDB:` A NoSQL database used to store dynamic data for the application.
- `Amazon CloudFront:` A content delivery network (CDN) that caches your web application's assets globally for improved performance and security.

### Architecture Overview

#### The serverless web application consists of:

1. `Static Hosting:` All static content (HTML, CSS, JavaScript) is hosted in an S3 bucket, while dynamic content is served by API Gateway and Lambda.
2. `API Layer:` API Gateway routes user requests to appropriate Lambda functions that process the request.
3. `Compute Layer:` AWS Lambda processes requests with backend logic and communicates with DynamoDB for data storage/retrieval.
4. `Data Layer:` DynamoDB stores the application’s dynamic data in a NoSQL format, ensuring low-latency access.
5. `Edge Delivery:` CloudFront distributes static content and API calls to users globally with low latency, enabling fast response times.

### Step-by-Step Guide


#### Step 1. Setting Up Amazon S3 for Static Web Hosting
Create an S3 Bucket:
- Go to the S3 console and create a new bucket with a unique name.
- Set the bucket to public access (for public-facing websites).
- Upload your static assets (HTML, CSS, JavaScript, images) to the S3 bucket.
- Configure Bucket for Website Hosting:

- In the bucket settings, enable static website hosting.
Set your index document (e.g., index.html) and an error document (e.g., error.html).
- Set Permissions:
update the bucket policy to allow public access to the static content.

