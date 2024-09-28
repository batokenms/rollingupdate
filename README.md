# rollingupdate

NGINX Deployment and Service:

This deploys NGINX with 10 replicas and exposes it through a service using a NodePort type.

Apache Deployment and Service:

Similarly, this deploys Apache with 10 replicas and exposes it using its own service.

Rolling Updates: You can use the same deployment structure for both applications, and update the image in the deployment manifest to perform a rolling update.

Applying the Configuration

Save the YAML for the NGINX deployment and service in nginx-deployment.yaml and apply it:

# kubectl apply -f nginx-deployment.yaml

Save the YAML for the Apache deployment and service in apache-deployment.yaml and apply it:

# kubectl apply -f apache-deployment.yaml

These two deployments and services will allow you to run both NGINX and Apache independently, exposing each via separate services. 

If you want to transition from NGINX to Apache using a rolling update, simply modify the existing deployment to replace the NGINX image with Apache and redeploy it.

# Roll the update 
Update the nginx:latest image to nginx:stable-perl
