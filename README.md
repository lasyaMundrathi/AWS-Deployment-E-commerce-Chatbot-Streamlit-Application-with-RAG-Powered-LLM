# AWS-Deployment-E-commerce-Chatbot-Streamlit-Application-with-RAG-Powered-LLM


## DEMONSTRATION

https://github.com/user-attachments/assets/dfb33911-1032-41d2-86c2-2486b40892ba

AWS E-commerce Chatbot Architecture
Architecture Components
Frontend/User Interaction Layer

Streamlit Application:
The Streamlit app (app.py) acts as the interface for end-users to interact with the chatbot.
It sends user queries to the backend hosted in Amazon ECS.
CI/CD and Containerization

GitHub Repository:

Stores the codebase, including Python scripts, workflows, and the Dockerfile.
CI/CD pipeline in GitHub Actions (aws.yml) builds the Docker image and pushes it to ECR.
Amazon ECR (Elastic Container Registry):

Stores the Docker images for the chatbot backend (ecommerce-repo).
GitHub Actions CI/CD:

Automates the pipeline for:
Building Docker images.
Pushing them to Amazon ECR.
Deploying the updated container to ECS.
Backend/Compute Layer

Amazon ECS (Elastic Container Service):

Runs the containerized backend on AWS Fargate, which is fully managed and serverless.
Task Definition specifies the containerized application configuration, including:
Environment variables (e.g., Pinecone, LangChain, Google API keys).
Resource allocation: CPU = 1024, Memory = 3072.
Port mapping: Port 8080 for Streamlit communication.
Pinecone Vector Database:

Stores product review embeddings for quick retrieval and similarity search.
The backend interacts with Pinecone using the LangChain library (langchain-pinecone).
AI-Powered Retrieval and Generation

Google Generative AI API:
Used for generating advanced chatbot responses based on the retrieved embeddings.
APIs are accessed via the LangChain integration (langchain-google-genai).
Secrets Management and Monitoring

AWS Secrets Manager:

Stores sensitive credentials like API keys for LangChain, Pinecone, and Google services.
These secrets are injected as environment variables into the ECS task during deployment.
Amazon CloudWatch:

Tracks logs and metrics for ECS services, container activity, and application errors.

