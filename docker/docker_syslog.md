# syslog

In the host machine update the file
/etc/docker/daemon.json

```json 
{
  "log-driver": "syslog",
  "log-opts": {
    "syslog-address": "udp://1.2.3.4:1111"
  }
}
```


- restart the docker 

