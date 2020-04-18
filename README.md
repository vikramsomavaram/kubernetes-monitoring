# kubernetes-Monitoring
Install monitoring stack, Prometheus and Grafana in Kubernetes

## Requirements:
- helm V3
- kubectl

## Setup:
- Execute k8s-monitoring shell file to install all the required components - ./k8s-monitoring
- This script will install prometheus and grafana and creates a namespace called monitoring in which all the required components will be installed
- Once all the pods and up and running, use port-forwarding to access grafana 

> export POD_NAME=$(kubectl get pods --namespace monitoring -l "app=grafana,release=grafana" -o jsonpath="{.items[0].metadata.name}")

> kubectl --namespace monitoring port-forward $POD_NAME 3000 

- Open http://localhost:3000 in your browser to see the Grafana login screen

- Feel free to adjust the values in monitoring/grafana/values.yaml file for adding ingress or any other modifications apart from default.
