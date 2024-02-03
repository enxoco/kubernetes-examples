In this example we are exploring the use case of deploying a single application into multiple environments.  We are using a super simple custom image here that just returns an arbitrary environment variable. You can run the example like so:

```BASH
# Create the image for the staging environment
docker build -t example-backend:staging --build-arg ENVIRONMENT=staging .

# Create the image for the production environment
docker build -t example-backend:staging --build-arg ENVIRONMENT=production .

# Next apply the manifests to create our staging and production app deployments

# Production
kubectl apply -f environments/production/backend-deployment.yaml -f environments/production/backend-service.yaml -f environments/production/frontend-deployment.yaml -f environments/production/frontend-service.yaml

# Staging
kubectl apply -f environments/staging/backend-deployment.yaml -f environments/staging/backend-service.yaml -f environments/staging/frontend-deployment.yaml -f environments/staging/frontend-service.yaml
    
```
