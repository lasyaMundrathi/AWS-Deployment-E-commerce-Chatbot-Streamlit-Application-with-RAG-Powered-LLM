# AWS E-commerce Chatbot: Streamlit + RAG-Powered LLM with CI/CD Deployment

## Why This Project Matters
Bring your e-commerce platform to life with an AI-powered chatbot that delivers personalized product recommendations and instant customer support. Built with cutting-edge technologies like **RAG pipelines, Pinecone embeddings, and Google Generative AI,** this project promises an intelligent, scalable, and secure solution.

---
## **AWS E-commerce Chatbot Architecture**
![AWSECOMMERCEARCHITECTURE](https://github.com/user-attachments/assets/701ded73-1e07-4e0d-a947-135e1cf0d76b)

---

## Highlights
1. **Frontend**:   A sleek **Streamlit interface** hosted on **Amazon ECS** for seamless user interactions.
2. **CI/CD Automation**:   **GitHub Actions** automates Docker image builds and deployments to **Amazon ECR**, streamlining development and operations.
3. **Backend**:  
   - **Amazon ECS with Fargate** ensures serverless, scalable deployment.  
   - **Pinecone Vector Database** provides fast and efficient product embedding retrieval.
4. **AI-Driven Responses**:  Powered by **Google Generative AI**, delivering context-aware, customer-centric responses.
5. **Secure and Monitored**:  
   - **AWS Secrets Manager** secures sensitive API keys.  
   - **Amazon CloudWatch** ensures performance and error monitoring.
---
## DEMONSTRATION

https://github.com/user-attachments/assets/dfb33911-1032-41d2-86c2-2486b40892ba

---
## **Deployment Steps**

1. Clone the repository: ```git clone https://github.com/<your-username>/<your-repo>.git cd <your-repo>```
2. Set up CI/CD pipeline in ```.github/workflows/aws.yml.```
3. Push Docker image to **Amazon ECR**: The pipeline automates this step on every commit.
4. Deploy to **AWS Fargate:** ```aws ecs describe-services --cluster <cluster-name> --services <service-name>```
5. Access the chatbot via the ECS-provided URL.
---

## **AWS Setup**

- Enable key AWS services: **ECR, ECS, Fargate, Secrets Manager, CloudWatch.**
- Create an ECR repository: ```bash aws ecr create-repository --repository-name ecommerce-repo --region <region>```
- Authenticate Docker to ECR: ```bash aws ecr get-login-password --region <region> | docker login --username AWS --password-stdin <repository-uri>```
- Configure ECS cluster and service.
---
