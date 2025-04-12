Session 5

Containers will not support auto-scaling.  
Scale-Up: When traffic increases, we need to increase the number of servers.  
Vertical Scaling: Increase system resources.  
Horizontal Auto Scaling: Add additional servers to the existing infrastructure.  
Scale-Down: When traffic decreases, remove additional servers.

Containers do not support load-balancing or self-healing.  
To overcome these limitations, orchestration tools are used.

Kubernetes is a container management tool used for managing all containers and performing automatic deployment.

Kubernetes features:  
1. Orchestration  
2. Auto scaling  
3. Load-balancing  
4. Self-healing  
5. Platform-independent

To automate Kubernetes, manifest files are used.

Create a jump server or web-in host:  
- Launch instance: tarun-bastionhost  
- Ubuntu 24.04 LTS, t2.micro  
- Create key-pair: tarun-bastionhost (RSA .ppk)  
- 30 GB storage

Install kubectl, eksctl, AWS CLI:  
- Use: https://github.com/Msocial123/EverNorth-DevOps-Training-Material/Install  
- Open putty -> vi cluster.sh -> paste script -> :wq  
- chmod 777 cluster.sh  
- sudo su  
- sh cluster.sh

Create IAM user:  
- User: tarun-Kubernetes  
- Assign Administrator Access  
- Download .csv file of credentials  

On server:  
- Run aws configure with credentials  
- Run:  
  eksctl create cluster --name tarun-cluster --version 1.31 --region ap-northeast-2 --nodegroup-name test-linux --node-type t2.micro --nodes 3 --nodes-min 3 --nodes-max 5 --managed

Kubernetes manages applications in clusters.

Cluster: Group of nodes (master and worker)

Master Node:  
- Takes care of overall cluster health  
- Components:  
  1. API Server: Manages requests  
  2. ETCD: Distributed key-value database  
  3. Controllers: Monitor desired vs actual state  
  4. Scheduler: Assigns pods to nodes  

Worker Node:  
- Where apps are deployed  
- Components:  
  1. Kubelet: Creates pods, communicates with master  
  2. Container Runtime: Pulls docker images, manages containers  
  3. Kube-Proxy: Handles networking and exposure

Pod:  
- Smallest deployable unit in Kubernetes  
- Runs applications and contains containers  

Install kubectl:  
- snap install kubectl --classic  
- aws eks update-kubeconfig --name tarun-cluster --region ap-northeast-2  
- kubectl get nodes

Kubernetes manifest file fields:  
1. API Version  
2. Kind  
3. Meta-Data  
4. Spec

CPU: 1 CPU = 1000 millicores  
Memory: 1 GB = 1024 MB

Commands:  
- kubectl apply -f pod.yml  
- kubectl get pods -o wide  
- kubectl describe pod sample-pod

Clone repo:  
- git clone -b master https://github.com/gagan5423/tarun-kubernetes-manifestfiles.git

Deployments:  
- kubectl apply -f userprofile-deployment.yml  
- kubectl apply -f usernode-js-service.yml  
- kubectl get deployments  
- kubectl get svc

Access app at:  
ac6b997f103d846618fdf3442e10b5da-1008850829.ap-northeast-2.elb.amazonaws.com:3130