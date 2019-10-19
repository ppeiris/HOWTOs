# systemd

Systemd manage start and and stopping services. also, it manages how processes start at startup 

- Systemd use the word **units** and that has the same meaning as **deamon** 


#### List all the units and many other things in the system.
```
$ systemctl list-units
```

#### List only the services that are running in the system
```
$ systemctl list-units | grep .service 
```

#### Get a status of the a service 
```
$ systemctl status docker 
```

#### Disable services 
```
$ sudo systemctl disable docker
```

#### Stop services 
```
$ sudo systemctl stop docker 
```

#### Start services 
```
$ sudo systemctl start docker 
```

#### Restart services 
```
$ sudo systemctl restart docker 
```

#### List services that were failed to load 
```
$ systemctl --failed
```

#### Check if the service is enabled
```
$ systemctl is-enabled docker 
```

### Display Logs 

Query the systemd journal (logs)
```
$ journalctl 
```

#### Current boot logs 
```
$ journalctl -b 
```

#### Logs specific to service 
```
$ journalctl -u docker  
```










