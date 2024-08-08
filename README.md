# OceanSpy

<p align="center">
  <img src="src/media/logo.png" alt="Ocean Pollution Detector Logo" width="150"/>
</p>

- [Visit the Application 🌐](http://54.162.175.97:3000/)
- [Project PDF 📄](media/Project.pdf)

## Overview

The OceanSpy is a web application designed to detect and analyze pollution in the ocean using real-time image uploads and live camera detection. The application leverages AWS services to handle image uploads and analysis, providing users with insights into ocean pollution.

## Features

- **Upload Image**: Users can upload images of the ocean to detect pollution.
- **Live Detection**: Real-time detection using the webcam to periodically capture images and analyze them for pollution.
- **Responsive Design**: Mobile-friendly and designed for various screen sizes.

## Technologies Used

![React](https://img.shields.io/badge/React-20232A?style=flat&logo=react&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=flat&logo=vite&logoColor=ffffff)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=ffffff)
![AWS Lambda](https://img.shields.io/badge/AWS%20Lambda-232F3E?style=flat&logo=aws-lambda&logoColor=ffffff)
![AWS API Gateway](https://img.shields.io/badge/AWS%20API%20Gateway-232F3E?style=flat&logo=aws-api-gateway&logoColor=ffffff)
![AWS Rekognition](https://img.shields.io/badge/AWS%20Rekognition-232F3E?style=flat&logo=aws-rekognition&logoColor=ffffff)
![AWS S3](https://img.shields.io/badge/AWS%20S3-569A31?style=flat&logo=aws-s3&logoColor=ffffff)
![AWS SNS](https://img.shields.io/badge/AWS%20SNS-232F3E?style=flat&logo=aws-sns&logoColor=ffffff)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat&logo=github-actions&logoColor=ffffff)
![AWS ECS](https://img.shields.io/badge/AWS%20ECS-232F3E?style=flat&logo=aws-ecs&logoColor=ffffff)
![AWS ECR](https://img.shields.io/badge/AWS%20ECR-232F3E?style=flat&logo=aws-ecr&logoColor=ffffff)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=ffffff)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=ffffff)

- **Frontend**: React, Vite
- **Containerization**: Docker
- **Backend**: AWS Lambda, API Gateway
- **Image Processing**: AWS Rekognition
- **Storage**: AWS S3
- **Notifications**: AWS SNS
- **CI/CD**: GitHub Actions, AWS ECS, AWS ECR
- **Web Technologies**: HTML, CSS

## Architecture

![Architecture Diagram](media/Architecture.png)

## How It Works

### Image Upload and Processing Pipeline

1. **Image Upload**:
   - Users upload an image through the web interface.
   - The client-side React application sends an API request to AWS API Gateway.
   - The request triggers an AWS Lambda function that decodes and uploads the image to an S3 bucket.

2. **Image Processing**:
   - Upload to S3 triggers another AWS Lambda function.
   - This Lambda function processes the image using AWS Rekognition.
   - If the image is detected with pollution (confidence >= 80), a notification is sent via AWS SNS.

### Notification Subscription Pipeline

1. **User Subscription**:
   - Users subscribe to notifications by entering their email ID on the website.
   - The client application sends an API request via AWS API Gateway to an AWS Lambda function.
   - The Lambda function subscribes the user’s email to an AWS SNS topic.

### CI/CD Pipeline

1. **Code Commit**:
   - Every push to the GitHub repository triggers a GitHub Actions workflow.
   - The workflow builds a Docker image and pushes it to AWS ECR.
   - A new deployment is initiated in AWS ECS, which uses Fargate for instance management.

## Installation

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/your-username/Ocean-Pollution-Detector.git
   cd Ocean-Pollution-Detector

## Testing

1. Go to the application. On the home page, you will see "Upload Image" and "Subscribe" buttons.
2. Click on the "Subscribe" button, enter your email ID, and save.
3. You will receive a confirmation email from AWS. Confirm your subscription.
4. Click on "Upload Image" to submit an image.
5. If pollution is detected in the image, you will receive a notification email; otherwise, no email will be sent.

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Contact

Created by: Priya Mandyal
