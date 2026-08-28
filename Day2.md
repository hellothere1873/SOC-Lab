# Day 2

I configured a VPC along with one virtual ubuntu server in which I installed Elasticsearch.

I set a custom IP address for the VPC 172.31.0.0/24 and disabled automatic backups as they aren't required for the scope of this lab.

I created an instance (Server) inside the VPC with   
Ubuntu 22.04 x64 as the OS along with very little specs like 1 vCPU 2gb of RAM and 25GB of NVMe storage. In which then I SSH'ed into it via my computer via PowerShell with the username and password provided by the cloud provider I then updated the server with the relevant commands, set up Elasticsearch and started it. I then made a firewall group in which I specified that the only IP that can SSH into the server is my own.
