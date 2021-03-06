# Kubernetes_EFK (EFK Stack for the K8s cluster)
Here, ElasticSearch (Storage)+ Fluentd (Logging Layer)+ Kibana (Visualization) will be used to store, aggregate & visualise logs.
EFK is being popularly used for logging in K8s. 

Following is the directory Structure of the Kubernetes_EFK.

#### Please note, Helm charts are not used here. Clone the repo and start creating the objects. 

> 1) Create namespace - logging. 
This ns is dedicated to the logging environment. I have create here namespace using command, but in prod environment this should be created with yaml with resource limitation.
```
# kubectl create ns logging
```
> 2) Create PV for the ES (Please note here peristent volumes are actually hostPath volumes. You need to use the actual volumes ) 
```
# vi es-pv.yaml 
# kubectl create -f es-pv.yaml 
```
> 3) Create PVC for ES (Create PVC which will be bound to the PV)
```
# vi es-pvc.yaml 
# kubectl create -f es-pvc.yaml 
```
> 4) Create Statefulset of ES   

```
# vi es-statefulset.yaml 
# kubectl create -f es-statefulset.yaml 
```
> 5) Create Service for ES (Once the service is deployed you can do curl to the 9200 port of service - 10.101.181.175:9200/_cluster/health )


