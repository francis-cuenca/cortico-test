# cortico-test
Take Home Test for DevOps

## Web Server Monitoring

### Architecture
![alt text](resources/architecture.png)

The system will be using cAdvisor to gather real time metrics and Prometheus to scrape the metrics. Grafana's dashboard will be used for visualizing the scraped metrics.

This setup allows for effective scaling by automatically exposing container metrics to cAdvisor every time a new container is going to be added. Grafana can be used also for monitoring and analyzing data from metrics.

### Prerequisites 

#### Installing Docker Engine
Make sure to have Docker installed beforehand. A quick tutorial for installing Docker can be found in the docs [here](https://docs.docker.com/engine/install/).

### Running the System
To run the system simply clone the repo and run the `docker compose up` command:
```
git clone https://github.com/francis-cuenca/cortico-test.git
cd cortico-test
sudo docker compose up
```
Docker should then spin up the containers, which will look like this:
![alt text](resources/building-containers.png)

You can check the status of the containers using `sudo docker ps`.
```
CONTAINER ID   IMAGE                             COMMAND                  CREATED             STATUS                   PORTS                                       NAMES
ea683d862ca8   grafana/grafana                   "/run.sh"                42 minutes ago      Up 2 minutes             0.0.0.0:8002->3000/tcp, :::8002->3000/tcp   cortico-test-grafana-1
36eefac6a43b   prom/prometheus                   "/bin/prometheus --c…"   59 minutes ago      Up 2 minutes             0.0.0.0:8001->9090/tcp, :::8001->9090/tcp   cortico-test-prometheus-1
e8a5513e03c5   gcr.io/cadvisor/cadvisor:latest   "/usr/bin/cadvisor -…"   59 minutes ago      Up 2 minutes (healthy)   0.0.0.0:8003->8080/tcp, :::8003->8080/tcp   cadvisor
debf9c0a54f8   cortico-test-web                  "flask run --debug"      About an hour ago   Up 2 minutes             0.0.0.0:8000->5000/tcp, :::8000->5000/tcp   cortico-test-web-1
675900dfab94   redis:alpine                      "docker-entrypoint.s…"   2 hours ago         Up 2 minutes             6379/tcp                                    cortico-test-redis-1
```
### Checking the Grafana dashboard

The Grafana dashboard will be available once the container is up in the address [https://localhost:8002](https://localhost:8002). You will then be able to see the login screen like so:
![alt text](resources/grafana-login.png)

You can login using these credentials:

username: `admin`

password: `password`

You will then be brought to the home page:
![alt text](resources/grafana-landing.png)
