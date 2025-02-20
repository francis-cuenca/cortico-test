# cortico-test
Take Home Test for DevOps

## Web Server Monitoring

### Architecture
![alt text](resources/architecture.png)

The system will be using Prometheus for monitoring the Web app's metrics and Grafana's dashboard will be used for visualizing the scraped metrics.

This setup allows for effective scaling by exposing container metrics to Prometheus every time a new container is going to be monitored.

### Prerequisites 

#### Installing Docker Engine
Make sure to have Docker installed beforehand. A quick tutorial for installing Docker can be found in the docs [here](https://docs.docker.com/engine/install/).

