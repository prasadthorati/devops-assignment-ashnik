# devops-assignment-ashnik
Using the playbook.yaml we can install Prometheus and Grafana on server hosts specified on the inventory file
ansible-playbook playbook.yml

we can add the node details on prometheus.yaml by default file located in /etc/prometheus/
In this file "prometheus.yml" I have added node exporter and JMX exporter configuration

Access the Prometheus with the port 9090 (default)
Access the Grafana using the 3000 (default) port
Login grafana using the credentilas
Add the data source of Prometheus and create the dashboards. using this file "grafana_metrics-json.json" we can configure node and application metrics.
Application metrics configured with the help of JMX exporter. I have deployed the application with the help of a Java agent with JMX exporter.
java -javaagent:./jmx_prometheus_javaagent-0.20.0.jar=12345:config.yaml -jar demo.jar

We have configured alerts using the Grafana using the alert policies. Based on threshold we can configure the alerts. I have created an alert rule for CPU utilization 50% above. Please refer to the attached JSON "alertrule.crdownload"
