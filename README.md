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

  
**Deployment commands:**

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml

**- Monitor**
CloudWatch Logs are used to monitor:

CodeBuild logs
Deployment execution logs
Application logs

**Technologies Used**
GitHub
AWS CodePipeline
AWS CodeBuild
Amazon EKS
Kubernetes
Docker
Amazon CloudWatch
