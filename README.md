# AWS-Serverless-AI-ML-Integration-Suite

A collection of serverless, event-driven workflows built on AWS. This repository demonstrates how to architect automated data pipelines using AWS services such as S3, Lambda, SQS, and SNS, integrated with AI/ML tools like Amazon Polly, Transcribe, and Comprehend.


## Project Overview ##
This project showcases the implementation of automated workflows triggered by system events. By leveraging a serverless architecture.


Included Workflows
| Feature | Trigger | AWS Services Used |
| :--- | :--- | :--- |
| **Audio Synthesis** | S3 File Upload | S3, Lambda, Amazon Polly |
| **Media Transcription** | S3 File Upload | S3, Lambda, Amazon Transcribe |
| **Sentiment Analysis** | SQS Message | SQS, Lambda, Amazon Comprehend, SNS |



## Architecture Details ##
Audio Synthesis: When a text file is uploaded to the source S3 bucket, a Lambda function triggers Amazon Polly to convert the text into an audio file, which is then stored in the destination S3 bucket.
Media Transcription: A video upload to S3 triggers a two-stage process: first, Amazon Transcribe generates a JSON transcript; then, a secondary Lambda function parses this into a human-readable .txt file.
Sentiment Analysis: Reviews are sent to an SQS queue, which triggers a Lambda function. The function processes the text using Amazon Comprehend for sentiment analysis and uses Amazon SNS to email the results.



## Technical Stack ##
Languages: Python
Core Services: AWS Lambda, Amazon S3, Amazon SQS, Amazon SNS
AI/ML Services: Amazon Polly, Amazon Transcribe, Amazon Comprehend
Architecture: Serverless, Event-Driven

