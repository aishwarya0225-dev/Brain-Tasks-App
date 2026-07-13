## 🚀 AWS CI/CD Pipeline Architecture

This project uses AWS services to automate application deployment.

Flow:

GitHub Repository
        |
        ↓
AWS CodePipeline
        |
        ↓
AWS CodeBuild
        |
        ↓
Amazon EKS Cluster
        |
        ↓
Kubernetes LoadBalancer Service


## 🔄 Pipeline Stages

### 1. Source Stage
- Source provider: GitHub
- Code changes trigger the pipeline execution.

### 2. Build Stage
- AWS CodeBuild is used for build execution.
- Build instructions are defined in `buildspec.yml`.
- Build logs are monitored using Amazon CloudWatch Logs.

### 3. Deploy Stage
- AWS CodePipeline deploys the application to Amazon EKS.
- Kubernetes manifest files used:
