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

kubectl apply -f deployment.yaml
kubectl apply -f service.yaml

### Kubernetes Verification

Check pods:

kubectl get pods

Check service:

kubectl get svc

### Monitoring

CloudWatch Logs are used to monitor:
- CodeBuild logs
- Deployment logs
- Application logs

### Technologies Used

- GitHub
- AWS CodePipeline
- AWS CodeBuild
- Amazon EKS
- Kubernetes
- Docker
- Amazon CloudWatchDevOps Practice Project – Dist Directory


