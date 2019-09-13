# Milton-Kubernetes-Assignment
Welcome to my Kubernetes assignment. This assignment is for a Kubernetes configuration scripts and commands to deploy a clusters and two Pods

Type the following commands to set environment variables 
export my_zone=us-central1-a
export my_cluster=assignment-cluster

To create the Kubernetes Cluster
gcloud container clusters create $my_cluster --num-nodes 2 --zone $my_zone --enable-ip-alias

To create a kubeconfig file with my user credentials 
gcloud container clusters get-credentials $my_cluster --zone $my_zone

This command creates a .kube directory in your home directory if it doesn't already exist. In the .kube directory, the command creates a file named config if it doesn't already exist, which is used to store the authentication and configuration information. The config file is typically called the kubeconfig file.

Execute this command to view the contents of the kubecofig file
kubectl config view

Type the following command to print out the cluster information
kubectl cluster-info

Execute the following command to view the resource usage across the nodes of the cluster
kubectl top nodes

Deploy Pods

Issue the following command to deploy the latest version of nginx as a Pod named nginx-1
kubectl run nginx-1 --image nginx:latest

Execute the following command to view all the deployed Pods in the active context cluster
kubectl get pods

To confirm that you have set the environment variable successfully by having the shell echo the value back to you
echo $my_nginx_pod

To view the complete details of the Pod you just created
kubectl describe pod $my_nginx_pod

Expose the Pod to be accessed externally
kubectl expose pod $my_nginx_pod --port 80 --type LoadBalancer

Execute the following command to view details about services in the cluster
kubectl get services

End.
