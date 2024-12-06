snap install aws-cli --classic 
curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp~
curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp
sudo mv /tmp/eksctl /usr/local/bin
eksctl version
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
chmod +x kubectl
 mkdir -p ~/.local/bin
   11  mv ./kubectl ~/.local/bin/kubectl
   12  kubectl version --client
   13  aws confugure
   14  aws configure
   
   16  eksctl create cluster --name demo-ekscluster --region ap-south-1 --version 1.27 --nodegroup-name Linux-nodes --node-type t2.micro --nodes 2
   17  kubectl get nodes
     19  aws eks update-kubeconfig --name demo-ekscluster
   20  kubectl get nodes
   21  nano pod.yaml
   22  kubectl apply -f pod.yaml 
   23  kubectl get pod
   24  kubectl get pod -o wide
   25  kubectl get svc
   26  nano pod.yaml
   27* kubectl get svc
   28  kubectl exec -it mypod -- bash
   29  nano pod.yaml
   kubectl apply -f pod.yaml 
   23  kubectl get pod
   24  kubectl get pod -o wide
   25  kubectl get svc
   26  nano pod.yaml
   27* kubectl get svc
   28  kubectl exec -it mypod -- bash
   29  nano pod.yaml
   30  y
   31  kubectl get svc
   32  kubectl get pod -o wide
   33  kubectl exec -it mypod -- bash
   34  history 



POD_IP=$(kubectl get pod my-pod -o jsonpath='{.status.podIP}')
