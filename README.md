### hvmon

Docker-compose file with components needed for harmony validator nodes monitoring.
Grafana, Prometheus, Node exporter.
Should be located on separate dedicated host.
docker and docker-compose packages are required to use this project.

Installation guide: 

```
$ git clone https://github.com/itowerONE/hvmon.git
$ cd hvmon
```

Edit configuration files to meet your needs:

```
  * alertmanager/alertmanager.yml
         smtp_smarthost
         smtp_from
         smtp_auth_username
         smtp_auth_password
         email address to in receivers section

  * docker-compose.yml
         set correct IP addresses for extra_hosts for prometheus service
         set your password for Grafana admin user in ADMIN_PASSWORD property
 
  * prometheus/file_sd/
         if you need to add more monitored nodes, you should add additional 
         target files into file_sd directory, add additional IP addresses 
         into extra_hosts for prometheus service in docker-compose.yml file as well.
```

When configuration is done start up containers with command:

```
$ docker-compose up -d
```

