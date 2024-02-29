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

Install mysql to change the default db sqlite to mysql db to store the logs
documentation https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-20-04

# For grafanadb backup
in mysql give the process priveleges to grafana user.
```mysql
GRANT PROCESS ON *.* TO 'grafana'@'localhost';
Query OK, 0 rows affected (0.00 sec)

mysql> flush privileges;
Query OK, 0 rows affected (0.01 sec)
```
```sh
 mysqldump -u grafana -h localhost -pgrafana@123 grafanadb > /home/grafanaadmin/grafana.sql
```
edit in this file ```/etc/grafana/grafana.ini``` and port to 3010 for grafana

```sh
#Either "mysql", "postgres" or "sqlite3", it's your choice
type = mysql 
host = localhost:3306
name = grafanadb
user = grafana
```
