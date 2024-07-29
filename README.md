# EFK

kubectl create ns fluentd
#configmap fluentd
kubectl apply -f fluentd-configmap.yaml
**#Fluentd Daemonset**
kubectl apply -f fluentd-rbac.yaml 
kubectl apply -f fluentd.yaml
kubectl -n fluentd get pods
**#Demo ElasticSearch and Kibana**
kubectl create ns elastic-kibana

# deploy elastic search
kubectl -n elastic-kibana apply -f elastic-demo.yaml
kubectl -n elastic-kibana get pods

# deploy kibana
kubectl -n elastic-kibana apply -f kibana-demo.yaml
kubectl -n elastic-kibana get pods
**#Kibana**
kubectl -n elastic-kibana port-forward svc/kibana 5601
