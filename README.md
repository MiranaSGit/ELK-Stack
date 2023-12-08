# ELK (Elasticsearch-Logstash-Kibana) Stack Deployment
This repo is for deploying ELK stack by related Helm Chart.

## Installing
This chart is tested on docker-desktop with the 7.15.0 version.

1. Add the helm repo

```
helm repo add elastic https://helm.elastic.co 
```

2. Deploy elasticsearch

```
helm install elasticsearch elastic/elasticsearch --version="7.15.0" -f ./elasticsearch/values.yaml
```
3. Deploy filebeat 

```
helm install filebeat elastic/filebeat --version="7.15.0" -f ./filebeat/values.yaml
```
4. Deploy logstash.

```
helm install logstash elastic/logstash --version="7.15.0" -f ./logstash/values.yaml
```
5. Deploy kibana. 

```
helm install kibana elastic/kibana --version="7.15.0" -f ./kibana/values.yaml
```
6. Check the pods and make sure all pods are running.

7. Forward Kibana service port to localhost
```
kubectl port-forward svc/kibana-kibana 5601
```
8. Access the Kibana Dasboard on the localhost via a web browser
```
http://localhost:5601
```