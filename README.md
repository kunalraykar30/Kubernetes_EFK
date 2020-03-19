# Kubernetes_EFK
EFK 

1) Create namespace - logging. 
This ns is dedicated to the logging environment. I have create here namespace using command, but in prod environment this should be created with yaml with resource limitation.
# kubectl create ns logging

2) Create PV for the ES (Please note here peristent volumes are actually hostPath volumes. You need to use the actual volumes ) 
# vi es-pvc.yaml 
# kubectl create -f es-pvc.yaml 

3) Create PVC for es
4) Create Statefulset of ES   
5) Create Service for ES (Once the service is deployed you can do curl to the 9200 port of service - 10.101.181.175:9200/_cluster/health )

