## AWS CI/CD Pipeline

This project uses AWS services to automate application deployment.

### Pipeline Flow

GitHub → AWS CodePipeline → AWS CodeBuild → Amazon EKS → Kubernetes LoadBalancer

### Pipeline Stages

**Source Stage**
- Source code is maintained in GitHub repository.

**Build Stage**
- AWS CodeBuild builds the application using buildspec.yml.
- Build logs are monitored using Amazon CloudWatch Logs.

**Deploy Stage**
- Application is deployed to Amazon EKS using Kubernetes manifests:
  - deployment.yaml
  - service.yaml

Deployment commands:

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
