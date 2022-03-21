# Prometheus-Freepbx Asterisk 18
Quick setup of prometheus monitering for freepbx(asterisk 17+)
Asterisk 17+ has native support for prometheus using the module res_prometheus

## Changeing asterisk version freepbx
If asterisk version `code` is below 17, change the asterisk version using `code`

## Add module to freepbx 
Add the res_prometheus.so to the UI `Admin > Asterisk Module > Add Module > res_prometheus.so`
This tells asterisk to load the prometheus module
**Dont Restart asterisk yet**

## Make the config file
Make the config file using the UI `Admin > Config Edit > Asterisk System Configuration File > New File > prometheus.conf`

Put this in the file 
```
[general]
enabled = yes
core_metrics_enabled = yes
uri = metrics
```
## Make Sure that the asterisk mini http server is on 

Check that it is enable `Settings > Advanced Settings > Asterisk Builtin mini-HTTP server > Enable the mini-HTTP Server` 
note the port that the server is running on

You should be able to access the metrics on http://ip:port/metrics

# Node Exporter
