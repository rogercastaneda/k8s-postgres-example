# Requirements
```
brew install hyperkit minikube
```

# Start in mac using minikube
```
minikube start --vm-driver=hyperkit
minikube addons enable ingress
```

# Apply 
```
k apply -f postgresql-configmap.yaml
k apply -f postgresql.yaml
k apply -f postgresql-service.yaml
```

# Connect to db 
## Expose service

```
minikube service postgres-db-lb --url
```
The result will be similar to:
http://192.168.64.5:32615

Use dbeaver or any tool to connect to that server:port using the user/pass in the configmap.