Grafana dashboards.
Grafana is a tool that is used for visualization purposes we can use it and also integrate Prometheus as the data source in order to monitor our servers

node-exporter-system-metrics, see: https://grafana.net/dashboards/405

 INSTALLATION Process:
create file with command sudo vi /etc/yum.repos.d/grafana.repo
[grafana]
name=grafana
baseurl=https://packages.grafana.com/enterprise/rpm
repo_gpgcheck=1
enabled=1
gpgcheck=1
gpgkey=https://packages.grafana.com/gpg.key
sslverify=1
sslcacert=/etc/pki/tls/certs/ca-bundle.crt
//install grafana
sudo yum install grafana
//start grafana
sudo systemctl daemon-reload
sudo systemctl start grafana-server
sudo systemctl status grafana-server
sudo systemctl enable grafana-server
systemctl edit grafana-server.service
Now navigate to localhost:3000 or ip:3000
example http://54.158.11.249:3000/

Create/ Modify Dashboard: ( https://blog.devops.dev/how-to-set-up-monitoring-using-prometheus-and-grafana-tools-in-aws-f6d53cafcb0f)
To add a data source click on setting > data source and add Prometheus as a data source.
Click on explore and choose query to check the metrics
example select from the dropdown up and execute the query.
We can create a custom dashboard in order to monitor the metrics.
Navigate to Dashboard > Import option> paste the dashboard URL (https://grafana.com/grafana/dashboards/405-node-exporter-server-metrics/) and load.
