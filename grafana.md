# Grafana
- Installing grafana from official documentation
- change the port from `/etc/grafana/grafana.ini` file
- In grafana the ini file has `;` for commenting the directives.
- default username and password is admin
```sh
  sudo systemctl start grafana-server.service -> for starting
  sudo systemctl stop grafana-server.service -> for stopping
  sudo systemctl restart grafana-server.service -> for restarting
```
Successfully changed the port!! from default 3000 to 3010 port

![image](https://github.com/mallikharjuna160003/30-Days-of-AWS/assets/74324685/b77c0fe4-27ab-46ba-a57a-1ce2c9e97059)
