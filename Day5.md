I spun up a fleet-server on Ubuntu 22.04 x64 as the OS, I attached it the SOC lab VPC, without any firewall rules/group.
I went through the process of adding that server as a fleet server in the Elasticsearch GUI through our Elasticsearch and Kibana server the process was that I had to install the elastic agent configured with the fleet policy everything was pretty simple with due to the ease of use from the GUI and the ready to copy and paste commands.
I then added the windows-server I created on day 4 as an agent went through pretty much the same process, I had to install the elastic agent configured with the agent policy. There were however some problems with the installation and more specifically the enrollment, I had a self-signed certificate so I was hit with the error: Error: fail to enroll: fail to execute request to fleet-server: x509: certificate signed by unknown authority. Fixing it was easy I just had to type this flag at the end: --insecure, to ignore certification, for some reason though trying enrollment after the installation had finished resulted in the following error: Restart attempt 2 failed: 'rpc error: code = Unavailable desc = connection error: desc = \"transport: Error while dialing: open \\\\.\\pipe\\elastic-agent-system: The system cannot find the file specified. I tried to getting it working, but I decided to just reinstall and type --insecure from the beginning and that seemed to fix it.




On the elk-server(elastic and kibana server) I did ufw allow 9200 and allowed the windows-server IP to send log info from port 9200 via the Vultr firewall group so that the elk-server is able to view the windows-server's logs.

I allowed the fleet-server to send packets through every port on the elk server via the Vultr firewall group.

I specified the fleet-server URL, essentially to what fleet manager the agents belonged in, via the settings tab of the fleet in the Elasticsearch GUI and more specifically the port 8220 (https://fleetserverIP:8220) that's the default for agents. Kibana had autoconfigured it to https 443 so I had to change it.

I set ufw allow 8220 for the fleet-server to be able to communicate with the agent windows-server


Windows-server communicates via port 9200 with the elk-server and sends logs to it
Windows-server connects via port 8220 to the fleet-server 
