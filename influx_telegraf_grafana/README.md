Configure InfluxDB
```
docker run --rm influxdb influxd config > /opt/influxdb.conf
```

Configure Telegraf
```
docker run --rm telegraf telegraf config > /opt/telegraf.conf
Modify telegraf.conf:
  urls = ["http://127.0.0.1:8086"]
```

Run `docker-compose up -d`

Configure Grafana
* Login on http://<ip>:3000
* Username/Password admin/admin
* Add a InfluxDB data source (http://influxdb:8086), database telegraf, no auth
* Add Dashboard 1443 and see if things work
