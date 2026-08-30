I spun up a fleet server on Ubuntu 22.04 x64 as the OS, I attached it the SOC lab VPC, without any firewall rules.

On the elk stack(elastic and kibana server) I did ufw allow 9200 and allowed the windows server IP to send log info from port 9200 via the Vultr firewall group for Elasticsearch to function.

allowed the fleet to access the elk server and more specifically 9200 elasticsearch so we allowed it to communicate with the fleet server



I specified the fleet server url in the settings tab of the fleet in the elasticsearch gui and more specifically the port 8220 https://fleetserverIP:8220 that's the default for agents and it kibana had autoconfigured it to https 443 so I had to change it.

I set ufw allow 8220 for the fleet server and allowed the 
