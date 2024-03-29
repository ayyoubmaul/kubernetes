# How to
## Namespace
2. Craete namespace: `kubectl create ns postgres` or `kubectl create namespace postgres`
3. Check namespace: `kubectl get ns` or `kubectl get namespace`

## Configmap
1. Create configmap.yaml to define the postgres user, pass, and database configuration
2. Create the configmap: `kubectl apply -f configmap.yaml -n postgres`
3. Check the applied configmap: `kubectl get configmap -n postgres`
4. Get YAML configuration for the postgres configmap: `kubectl get configmap/postgres-secret -o yaml -n postgres`

## PersistentVolume and PersistentVolumeClaim
1. Create pv.yaml as PersistentVolume configuration
2. Create pvc.yaml as PersistentVolumeClaim configuration
3. Create the PersistentVolume resource: `kubectl apply -f pv.yaml -n postgres`
4. Create the PersistentVolumeClaim resource: `kubectl apply -f pvc.yaml -n postgres`
5. Check the applied PersistentVolume and PersistentVolumeClaim: `kubectl get pv,pvc -n postgres`
6. Get YAML configuration for the PersistentVolume: `kubectl get pv/postgres-volume -o yaml -n postgres`
7. Get YAML configuration for the PersistentVolumeClaim: `kubectl get pvc/postgres-volume-claim -o yaml -n postgres`

## Deployment
1. Create deployment.yaml as Deployment configuration
2. Create the Deployment resource: `kubectl apply -f deployment.yaml -n postgres`
3. Check the applied Deployment: `kubectl get deployment -n postgres`
4. Get YAML configuration for the Deployment: `kubectl get deployment/postgres -o yaml -n postgres`
5. Check the Pod status: `kubectl get pod -n postgres`
6. Get YAML configuration for the Pod: `kubectl get pod/<pod_name> -o yaml -n postgres`

## See Events
Get event on namespace: `kubectl get events -n postgres`
Get event on deployment: `kubectl get events -n postgres -l app=postgres`
Get event on pod: `kubectl get events -n postgres -l app=postgres,tier=web`

## Create Services
1. Create service.yaml as Service configuration
2. Create the Service resource: `kubectl apply -f service.yaml -n postgres`
3. Check the applied Service: `kubectl get service -n postgres`
4. Get YAML configuration for the Service: `kubectl get service/postgres -o yaml -n postgres`
5. Check the Service endpoint: `kubectl get endpoints -n postgres`

# Expose service
1. `kubectl port-forward service/postgres-service 5432:5432 -n postgres`


# Cleaning Everything
`kind delete cluster --name my-cluster`
