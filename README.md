# Udagram App into Microservices and Deploy
## Description
The project will highlight the ability to build microservice and cloud native application. The process will loosely follow a development flow used by lean, quick start ups.

## need Install
- [Docker](https://docs.docker.com/docker-for-mac/)
- [Kubectl](https://docs.aws.amazon.com/eks/latest/userguide/install-kubectl.html)
- [Eksctl](https://docs.aws.amazon.com/eks/latest/userguide/getting-started-eksctl.html)
- [Awsctl](https://docs.aws.amazon.com/cli/latest/userguide/install-macos.htmll)

#### setup docker env
- Build images and run containers:  
'docker-compose -f docker-compose-build.yaml  build --parallel'
'docker-compose up'

#### creating a cluster 
```
eksctl create cluster \
--name prod \
--version 1.14 \
--nodegroup-name standard-workers \
--node-type t3.medium \
--nodes 3 \
--nodes-min 1 \
--nodes-max 4 \
--node-ami auto
```
#### setup Kubernetes env
- Apply all yaml files:
    - 'kubectl apply -f . '

#### check pods status , connecting the servies 
-   'kubectl get all'
-  'kubectl port-forward service/frontend 8100:8100'



