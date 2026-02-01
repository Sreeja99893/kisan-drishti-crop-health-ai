Kisan Drishti – Technical Design Document

1. System Architecture Overview

    Kisan Drishti is built on a cloud-native, decoupled, event-driven architecture using AWS managed services.
    The system is designed to remain highly responsive, fault-tolerant, and cost-efficient, even during peak agricultural seasons when thousands of farmers may upload images concurrently.

    The architecture follows a serverless-first approach, minimizing operational overhead while enabling automatic scaling across geographies and crop cycles.

2. Infrastructure as Code (AWS Stack)
AWS Amplify (Frontend & Authentication)
    Used to host the mobile/web application and manage user login securely using Amazon Cognito.

Amazon S3 (Image Storage)
    Stores crop images uploaded by farmers. These images are used for real-time disease detection and for improving the AI model in the future.

AWS Lambda (Backend Compute)
    Automatically runs backend logic whenever a new image is uploaded, keeping costs low by running only when needed.

Amazon SageMaker (Machine Learning)
    Hosts and runs the AI model that analyzes crop images and identifies diseases specific to Indian crops.

Amazon DynamoDB (Metadata Storage)
    Stores disease information, treatment recommendations, dosage details, and language mappings.

Amazon Translate (Multilingual Support)
    Translates scientific treatment advice into regional Indian languages for farmers.

Amazon API Gateway (API Layer)
    Manages and secures all communication between the mobile app and backend services, including traffic control.

3. End-to-End Data Flow (Inference Pipeline)
Step 1: Image Ingestion

    The farmer captures a crop image using the mobile application.

    AWS Amplify securely uploads the image to an S3 bucket using pre-signed URLs.

Step 2: Event Trigger

    The successful image upload generates an S3 event.

    This event asynchronously invokes an AWS Lambda function.

Step 3: Image Validation & Preprocessing

    Lambda invokes Amazon Rekognition to verify that the image contains agricultural elements (e.g., leaves, crops, vegetation).

    Non-relevant images are discarded early to conserve compute resources.

Step 4: Model Inference

    The validated image is forwarded to a SageMaker real-time inference endpoint.

    The deep learning model (e.g., ResNet/Inception architecture) returns:

    Disease_ID

    Confidence_Score

Step 5: Localization & Intelligence Layer

Lambda queries DynamoDB using the Disease_ID.

Retrieves:

    Disease description

    Preventive measures

    Pesticide recommendations

    Dosage rules

    Content is localized using Amazon Translate based on the farmer’s preferred language.

Step 6: Response Delivery

    The enriched response is returned to the mobile client via API Gateway.

    The user receives diagnosis, treatment advice, and confidence indicators in under 3 seconds.

4. Scalability, Performance & Cost Optimization
4.1 Automatic Scaling

    AWS Lambda and SageMaker auto-scale to handle traffic spikes during harvest seasons.

    No manual provisioning required.

4.2 Edge & Offline Optimization (Planned)

    Future integration with SageMaker Neo enables model compression for on-device inference.

    Supports offline diagnosis in low or zero-connectivity regions.

4.3 Storage Optimization

    Images older than 30 days are transitioned automatically from S3 Standard to S3 Glacier using lifecycle policies.

    Reduces long-term storage costs while preserving historical data for retraining.

4.4 Traffic Management

    Amazon API Gateway enforces rate limiting and throttling.

    Protects backend services from traffic bursts and abuse.

5. Security, Privacy & Compliance
5.1 Data Security

    All images are encrypted at rest using AWS KMS.

    Data in transit is secured using HTTPS/TLS.

5.2 Privacy by Design

    No Personally Identifiable Information (PII) is stored alongside crop images.

    Location data is aggregated at the village or district level only.

5.3 Access Control

    Authentication and authorization are handled via Amazon Cognito.

    IAM roles enforce least-privilege access across services.

6. Design Philosophy

The system prioritizes:

    Low-latency inference

    Minimal farmer effort

    Resilience in poor network conditions

    Scalability across millions of users

Kisan Drishti is engineered not as a prototype, but as a foundation for national-scale agricultural intelligence.