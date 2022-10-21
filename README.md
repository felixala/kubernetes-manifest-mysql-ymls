# 1. Deploying MySQL Database in K8S Cluster
Follow the next steps to deploy Mysql in kubernetes using configmap, secrets, pv, pvc and db_deployment ymls.

## Create Config Map
```
$ kubectl apply -f <config-manifest-yml>
$ kubectl apply -f 1_weshopify-db-configmap.yml
```

## Create Secret
```
$ kubectl apply -f <secret-manifest-yml>
$ kubectl apply -f 2_weshopify-db-secret.yml
```

## Create PV : where we are going to save yhe data
```
$ kubectl apply -f <pv-manifest-yml>
$ kubectl apply -f 3_weshopify-db-pv.yml
```

## Create PVC : it will represent access
```
$ kubectl apply -f <pvc-manifest-yml>
$ kubectl apply -f 4_weshopify-db-pvc.yml

```

## Create Database Deployment
```
$ kubectl apply -f <database-manifest-yml>
$ kubectl apply -f 5_weshopify-db-deployment.yml
```

## Check pods which are created. Only database pod will be running
```
$ kubectl get pods
```

## Check services
```
$ kubectl get svc
```

## Check deployments
```
$ kubectl get deployment
```

## Check secret
```
$ kubectl get secrets
```

## Check pv
```
$ kubectl get pv
```

## Check pvc
```
$ kubectl get pvc
```

# 2. Getting databse mysql as a pod
With above steps, the databse deployment was completed. Now we want to connect to the Mysql datasbase using the pod.

## Getting all the pods names
```
$ kubectl get pods
```

## Connect to database pod
```
$ kubectl exec -it <pod-name-above-command> bash
```

# Connect to database
```
$ mysql -h localhost -u root -p
```
Note: It will ask for password, enter password as root.

## Check databases available in mysql
```
$ show databases;
```

## Use the database
```
$ use weshopify-app;
```

# create a table
```
$ create table emp(emp_id int, emp_name varchar(50));
```

# display all tables
```
$ show tables;
```

# insert record
```
$ insert into emp values(101, 'Raju');
$ insert into emp values(102, 'Rani');
```

## Retrieve records from table
```
$ select * from emp;
```

## exit from mysql database
```
$ exit
```

## exit from the pod
```
$ exit
```