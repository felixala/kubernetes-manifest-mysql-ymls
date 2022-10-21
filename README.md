Deploying MySQL Database in K8S Cluster

## Create Config Map
```
$ kubectl apply -f <config-manifest-yml>
$ kubectl apply -f 1_weshopify-db-configmap.yml
```

# Create Secret
$ kubectl apply -f <secret-manifest-yml>
$ kubectl apply -f 2_weshopify-db-secret.yml

# Create PV : where we are going to save yhe data
$ kubectl apply -f <pv-manifest-yml>
$ kubectl apply -f 3_weshopify-db-pv.yml

# Create PVC : it will represent access
$ kubectl apply -f <pvc-manifest-yml>
$ kubectl apply -f 4_weshopify-db-pvc.yml

# Create Database Deployment
$ kubectl apply -f <database-manifest-yml>
$ kubectl apply -f 5_weshopify-db-deployment.yml

# Check pods which are created
# Only database pod will be running
$ kubectl get pods

# Check services
$ kubectl get svc

# Check deployments
$ kubectl get deployment

$ kubectl get secrets

$ kubectl get pv

$ kubectl get pvc

