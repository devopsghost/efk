# efk
Repo to setup EFK(Elastic-Fluentd-Kibana) stack on K8S cluster

1. kubectl create namespace logging 
2. kubectl apply -f elasticsearch.yaml
3. kubectl apply -f kibana.yaml
4. kubectl apply -f fluentd.yaml
5. kubectl apply -f app.yaml
6. Get the Kibana service's external IP:
   kubectl get svc -n logging 
7. Open your browser and go to http://<KIBANA_IP>:5601
8. Configure Kibana to use the logs from Elasticsearch:
    Go to Management > Index Patterns.
    Create an index pattern matching the Fluentd index (e.g., logstash-*).