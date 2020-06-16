# Kubernetes Minikube Demo
Minikube demo deployment


Original from quay.io/ryanj/metrics-k8s
Thanks!


# USING

* Method #1
- Install deployment:
 - kubectl create -f deployment.yaml

* Method #2
- Install pod simply with json:
 - kubectl create -f pod.json
 - kubectl expose pods/metrics-k8s --port=2015 --type=NodePort
 - minikube service metrics-k8s --url



# TESING

* Check pod, service, deployment, replicaset:
- kubectl get pods,svc,deploy,rs


# TESTING Deployment

* Set scale:
- kubectl scale deploy/metrics-k8s --replicas=3


# REPLICASET, image rollout

* Upate image:
- kubectl set image deploy/metrics-k8s metrics-k8s=quay.io/ryanj/metrics-k8s:latest
- kubectl set image deploy/metrics-k8s metrics-k8s=quay.io/ryanj/metrics-k8s:v1
- kubectl get rs,deploy

* Check the history:
- kubectl rollout history deploy/metrics-k8s

* Rollout previously version:
- kubectl rollout undo deployment metrics-k8s

