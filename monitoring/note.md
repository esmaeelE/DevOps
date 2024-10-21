# Some prometheus notes

## Remove job from prometheus

First of all remove the job from `prometheus.yml`

Enable admin API in service or docker compose
`/etc/systemd/system/prometheus.service`

```
--web.enable-admin-api
```

Run below command
```
curl -u admin http://localhost:9090/api/v1/label/job/values -s | jq .

curl -X POST -g 'http://localhost:9090/api/v1/admin/tsdb/delete_series?match[]={job="node_exporter"}' -u admin

curl -X POST 'http://localhost:9090/api/v1/admin/tsdb/clean_tombstones' -u admin
```
Wait for about 5 minutes.


