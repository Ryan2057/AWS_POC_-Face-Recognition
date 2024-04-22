# Commands


- Install aws-shell
```
pip install aws-shell
```

- Configure
```
aws configure
```

- Create a collection on aws rekognition
```
aws rekognition create-collection --collection-id facerecognition_collection --region us-east-1
```

- Create table on DynamoDB
```
aws dynamodb create-table --table-name facerecognition
--attribute-definitions AttributeName=RekognitionId,AttributeType=S
--key-schema AttributeName=RekognitionId,KeyType=HASH
--provisioned-throughput ReadCapacityUnits=1,WriteCapacityUnits=1
--region us-east-1
```

- Create S3 bucket
```
aws s3 mb s3://bucket-name --region us-east-1
```
"# AWS_POC_-Face-Recognition" 


-------------------------------------------------------**DETAILED EXPLANATION**---------------------------------------------------


# AWS Facial Recognition POC

## Introduction
In this Proof of Concept (POC), we explore the implementation of facial recognition using AWS services such as Amazon S3, AWS Lambda, Amazon Rekognition, and Amazon DynamoDB. The goal is to demonstrate how these services can be integrated to build a facial recognition system that analyzes uploaded images, detects faces, and stores associated metadata in a database.

## Unique Advantages
This POC leverages the scalability, flexibility, and managed services provided by AWS to create a robust facial recognition solution. By using serverless computing with Lambda functions, coupled with AI-powered image analysis capabilities of Rekognition, developers can build powerful applications without the need to manage infrastructure. Additionally, DynamoDB offers seamless scalability and high availability for storing metadata associated with recognized faces.

## Real-Time Application
The facial recognition system developed in this POC has various real-time applications, including:
- Identity verification in security systems
- Personalized user experiences in applications
- Attendance tracking in educational institutions or workplaces
- Customer engagement and analysis in retail environments

## Conclusion
By following the procedures outlined in this POC, developers can set up an end-to-end facial recognition system using AWS services. The combination of S3 for storing images, Lambda for executing code, Rekognition for image analysis, and DynamoDB for metadata storage provides a comprehensive solution for facial recognition applications. This POC serves as a foundation for building more sophisticated and scalable facial recognition systems in production environments.

## Procedures

### Setting Up AWS Infrastructure:
1. **S3 Bucket Creation:**
   - Create a new S3 bucket in the AWS Management Console.
   - Configure bucket settings and permissions as required.
   
2. **DynamoDB Table Creation:**
   - Create a DynamoDB table to store metadata associated with recognized faces.
   - Define the table schema and provision read/write capacity based on expected workload.
   
### Configuring Lambda Function:
1. **Lambda Function Creation:**
   - Create a new Lambda function with an S3 trigger.
   - Write code to process uploaded images and invoke Rekognition for facial analysis.
   
2. **Lambda Function Code:**
   - Implement logic to extract faces from images and store metadata in DynamoDB.
   - Use AWS SDKs (e.g., Boto3 for Python) to interact with AWS services.
   
### Uploading Images:
1. **Python Script for Image Upload:**
   - Develop a Python script to upload images to the S3 bucket.
   - Set appropriate permissions and access control policies.
   
### Facial Recognition:
1. **Integration with AWS Rekognition:**
   - Configure Rekognition to analyze images and detect faces.
   - Utilize Rekognition APIs to extract facial features and match against known faces.
   
### Storing Metadata:
1. **DynamoDB Integration:**
   - Store metadata associated with recognized faces in DynamoDB.
   - Define table schema and insert/update items based on facial recognition results.
   
### Retrieving Results:
1. **Python Script for Retrieving Results:**
   - Develop a Python script to search for faces and retrieve metadata from DynamoDB.
   - Implement logic to handle different scenarios and visualize recognition results.

