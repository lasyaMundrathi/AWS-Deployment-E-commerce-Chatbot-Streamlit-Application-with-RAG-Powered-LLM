# AWS-Deployment-E-commerce-Chatbot-Streamlit-Application-with-RAG-Powered-LLM

## Overview

This project is an end-to-end deployment of an AI-powered chatbot tailored for e-commerce platforms. The chatbot leverages Retrieval-Augmented Generation (RAG) pipelines to provide product recommendations and customer support, combining data from product reviews and embeddings stored in Pinecone.

The project uses **Amazon Web Services (AWS)** for deployment, including:

- **Amazon ECR** for Docker image storage.
- **Amazon ECS** with Fargate for serverless application deployment.
- **GitHub Actions** for CI/CD automation.
- **AWS Secrets Manager** for secure credential management.
- **Amazon CloudWatch** for monitoring and logging.
---
## **AWS E-commerce Chatbot Architecture**
![AWSECOMMERCEARCHITECTURE](https://github.com/user-attachments/assets/701ded73-1e07-4e0d-a947-135e1cf0d76b)

---

## DEMONSTRATION

https://github.com/user-attachments/assets/dfb33911-1032-41d2-86c2-2486b40892ba


---

## **Architecture Components**

**Frontend/User Interaction Layer**
  - **Streamlit Application**: Provides a chatbot interface hosted on Amazon ECS.

**CI/CD and Containerization**
  - **GitHub Actions:** Automates Docker image builds and deployment to AWS.
  - **Amazon ECR:** Stores Docker images.

 **Backend/Compute Layer:**

- **Amazon ECS with Fargate:** Runs containerized backend with environment variables (e.g., Pinecone, LangChain).

- **Pinecone Vector Database:** Stores embeddings for efficient retrieval.

**AI-Powered Response Generation:**

- **Google Generative AI API:** Generates responses using embeddings via LangChain.

**Secrets Management and Monitoring:**

- **AWS Secrets Manager:** Manages sensitive credentials.
- **Amazon CloudWatch:** Monitors application logs and performance.
---
## **Deployment Steps**

**Clone the Repository:**

```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
```

**Set Up CI/CD Pipeline:**

- Configure ```.github/workflows/aws.yml``` for automated Docker builds and deployments.

**Push Docker Image:**

- The pipeline builds and pushes the Docker image to **Amazon ECR** on each commit.

**Deploy to Amazon ECS:**

- The service is deployed to AWS Fargate and can be verified via:

```aws ecs describe-services --cluster <cluster-name> --services <service-name>```

**Access the Chatbot:**

- Use the ECS-provided URL to interact with the Streamlit chatbot.
---
## **AWS Setup**

**Enable Required Services:**

- Elastic Container Registry (ECR), Elastic Container Service (ECS), AWS Fargate, Secrets Manager, and CloudWatch.

**Create an ECR Repository:**

```aws ecr create-repository --repository-name ecommerce-repo --region <region>```

**Authenticate Docker:**

```bash
aws ecr get-login-password --region <region> | docker login --username AWS --password-stdin <repository-uri>
```

**Set Up ECS Cluster and Service:**

- Create an ECS cluster and define a service for the chatbot.

**Configure Secrets:**

- Store API keys for Pinecone, LangChain, and Google Generative AI in **AWS Secrets Manager**.
