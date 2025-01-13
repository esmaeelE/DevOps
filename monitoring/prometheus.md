# Grafana dashborad reset password

```
sudo grafana-cli admin reset-admin-password admin
```

---


# Secure prometheus with basic auth and ssl

* I use nginx proxy manager as webserver and ssl termination.
* Obtain ssl from cloudflare and set nginx to use it wiht API key
* Reverse proxy to localhost prometheus web dashborad on 127.0.0.1:9090


* Basic Auth prometheus web dashborad

https://prometheus.io/docs/guides/basic-auth/


**gen-pass.py**
```
import getpass
import bcrypt

password = getpass.getpass("password: ")
hashed_password = bcrypt.hashpw(password.encode("utf-8"), bcrypt.gensalt())
print(hashed_password.decode())
```
Run to genrate password
```python3 gen-pass.py```



**web.yml**
```
basic_auth_users:
    admin: $2b$12$hNf2lSsxfm0.i4a.1kVpSOVyBCfIB51VRjgBUyv6kdnyTlgWj81Ay
```


```
promtool check web-config web.yml
```

**Check**
```
curl --head http://localhost:9090/graph
curl -u admin http://localhost:9090/metrics
```



# This is service 

$ sudo systemctl cat prometheus.service 
```
# Warning: prometheus.service changed on disk, the version systemd has loaded is outdated.
# This output shows the current version of the unit's original fragment and drop-in files.
# If fragments or drop-ins were added or removed, they are not properly reflected in this output.
# Run 'systemctl daemon-reload' to reload units.
# /etc/systemd/system/prometheus.service
[Unit]
Description=Prometheus
Wants=network-online.target
After=network-online.target

StartLimitIntervalSec=500
StartLimitBurst=5

[Service]
User=prometheus
Group=prometheus
Type=simple
Restart=on-failure
RestartSec=5s
ExecStart=/usr/local/bin/prometheus \
  --config.file=/etc/prometheus/prometheus.yml \
  --web.config.file=/etc/prometheus/web.yml \
  --storage.tsdb.path=/data \
  --web.console.templates=/etc/prometheus/consoles \
  --web.console.libraries=/etc/prometheus/console_libraries \
  --web.listen-address=127.0.0.1:9090 \
  --web.enable-lifecycle

[Install]
WantedBy=multi-user.target

```



