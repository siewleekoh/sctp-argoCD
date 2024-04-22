# sctp-argoCD  

Deploying a hello-world node.js application
1) deploy on ArgoCD using UI
   
   - create a public doccker image on ECR and a public github repo
   - point URL to ALB address with a domain name in Route 53
  
2) deploy on ArgoCD with helm chart
   ```
   helm create node-<your name>
   ```

   ```
   aws ecr get-login-password \
    --region us-east-1 | helm registry login \
    --username AWS \
    --password-stdin 255945442255.dkr.ecr.us-east-1.amazonaws.com
   ```

   ```
   Helm package node-<your name>
   ```

   ```
   ​​helm push node-<your name>-0.1.0.tgz oci://255945442255.dkr.ecr.us-east-1.amazonaws.com/
   ```
