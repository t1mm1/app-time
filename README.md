# Time Application

This application was originally developed as part of a Docker course, with a primary focus on using Docker Compose for orchestration and development. For added flexibility, Kubernetes manifests are also provided, enabling you to deploy the application on Kubernetes platforms such as Minikube.

For additional details and step-by-step guidance, check out the related courses:
Kubernetes Course: https://www.udemy.com/course/kubernetes-ru (Bogdan Stashchuk)
Docker Course: https://www.udemy.com/course/docker-ru (Bogdan Stashchuk)

## Support k8s running.

This is simple example of k8s integration for app-time application.

## Quick Start (Minikube)

### 1. Start Minikube

minikube start

### 2. Apply Kubernetes manifests

Be sure to set your own password and database name in secrets.yaml before applying!

```
kubectl apply -f namespace.yml -f secrets.yml -f mysql-pvc.yml -f mysql.yml -f api.yml -f frontend.yml -f adminer.yml
```

If you want to stop it, use:

```
kubectl delete -f namespace.yml -f secrets.yml -f mysql-pvc.yml -f mysql.yml -f api.yml -f frontend.yml -f adminer.yml
```

### 3. Check status

```
kubectl get pods -n app-time
kubectl get svc -n app-time
```

### 4. Open applications in your browser

### Frontend

```
minikube service -n app-time frontend
```

### Adminer (DB Web UI)

```
minikube service -n app-time adminer
```

## Notes

The default Kubernetes namespace is app-time.

## To remove all resources:

```
kubectl delete namespace app-time
```
