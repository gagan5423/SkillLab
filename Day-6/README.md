Session 6

*Namespace*  
A namespace is used to divide a single cluster into multiple isolated environments, allowing deployment of multiple applications on the same cluster.

*Check namespaces:*  
kubectl get namespace

*Default namespaces:*  
- default: Default workspace for resources.  
- kube-node-lease: For node health checks.  
- kube-public: Publicly accessible resources.  
- kube-system: Core Kubernetes components like DNS, CLI, metrics server.

*Important:* Never deploy applications to the default namespace in production.

*Creating a custom namespace:*  
1. kubectl create ns tarun-ns  
2. kubectl get ns  
3. kubectl run test-pod --image nginx --port 80 -n tarun-ns  
4. kubectl get pods -n tarun-ns  
5. kubectl delete pod test-pod -n tarun-ns

*Issues when a pod goes down:*  
1. Application downtime → use controllers.  
2. Pod IP changes → use Kubernetes services.  
3. Data loss → use Kubernetes volumes.

*Replica Set*  
A Kubernetes object that ensures a set number of pod replicas are always running.

1. git clone https://github.com/gagan5423/tarun-k86-manifestfiles.git  
2. cd tarun-k86-manifestfiles  
3. kubectl apply -f rs.yaml  
4. kubectl get pods -n tarun-ns  
5. kubectl get rs -n tarun-ns  
6. kubectl describe pod <pod-name> -n tarun-ns

*Add Node Group to Cluster:*  
AWS Console → EKS → Cluster (tarun-cluster) → Add Node Group  
- Name: test-linux-2  
- IAM Role  
- Launch Template  
- Instance type: 2 CPU, 4 GB RAM  
- Desired nodes: 3  
- Max nodes: 5  
- Enable auto-repair

*Replica Set limitations:*  
Cannot perform rollout/rollback → Use *Deployments* instead.

*Deployments:*  
Deployment manages Replica Sets, which in turn manage Pods.

1. kubectl delete rs cart-page-rs -n tarun-ns  
2. kubectl apply -f deployment.yaml -n tarun-ns  
3. kubectl get deployments -n tarun-ns  
4. kubectl get pods -o wide -n tarun-ns

*Kubernetes Services:*  
Used to expose applications. Types:  
1. ClusterIP  
2. NodePort  
3. LoadBalancer

*Example (LoadBalancer):*  
1. git pull  
2. kubectl apply -f service.yaml -n tarun-ns  
3. kubectl get svc -n tarun-ns

*Monitoring:*  
Helps track pod/node/cluster health and resource usage. Tools include:

- *Prometheus:* Collects time-series metrics (TSDB).
- *Grafana:* Displays metrics in dashboards (graphs, charts).

*Install Helm:*  
snap install helm --classic

*Prometheus setup in Grafana:*  
1. Add new data source → Prometheus  
2. Enter URL  
3. Dashboards → Import → ID: 15661

*Other commands:*  
1. kubectl get pods -n monitoring  
2. kubectl cluster-info  
3. kubectl get cluster  
4. cd /root/.kube  
5. vi config

*Ansible:*  
Configuration management tool used to automate system administration tasks.

*Delete cluster:*  
eksctl delete cluster --name tarun-cluster