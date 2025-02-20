# cortico-test
Take Home Test for DevOps

## Web Server Monitoring

### Architecture
![alt text](resources/Architecture.png)

The system will be using Prometheus for monitoring the Web app's metrics and Grafana's dashboard will be used for visualizing the scraped metrics.

This setup allows for effective scaling by exposing container metrics to Prometheus every time a new container is going to be monitored.

