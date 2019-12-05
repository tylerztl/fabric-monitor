# Hyperledger Fabric Monitoring with Prometheus and StatsD

## Start Fabric Network
```
docker-compose up -d
```

## Initialize Fabric Network
```
docker exec -it cli bash

./scripts/script.sh
```

## Start Prometheus and Grafana
```
docker-compose -f metrics-prometheus.yml up -d
```

You can access the [Prometheus UI](http://localhost:9090/targets) and [Grafana UI](http://localhost:3000/d/monitor/hyperledger-fabric-monitoring-for-1-4?orgId=1&refresh=5s)

## Start Statsd and Grafana
```
docker-compose -f metrics-statsd.yml up -d
```
Note: start statsd firstly and then start fabric network!

You can access the [Graphite UI](http://localhost) and [Grafana UI](http://localhost:3000/d/monitor/hyperledger-fabric-monitoring-for-1-4?orgId=1&refresh=5s)

# References
- https://hyperledger-fabric.readthedocs.io/en/release-1.4/operations_service.html
- https://hyperledger-fabric.readthedocs.io/en/release-1.4/metrics_reference.html
- [Hyperledger Fabric Monitoring with Prometheus and StatsD](https://medium.com/@jushuspace/hyperledger-fabric-monitoring-with-prometheus-and-statsd-f43ef0ab110e)
- [Monitoring Hyperledger Fabric components using Prometheus](https://medium.com/@ongkhaiwei/monitoring-hyperledger-fabric-components-using-prometheus-92e8bea1f51b)
- https://grafana.com/grafana/dashboards/10716
- https://github.com/graphite-project/docker-graphite-statsd
