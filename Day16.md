
I spun a windows 2022 standard edition server and installed XAMPP and osTicket on it, I am going to be refering to this instance as the osTicket-server.
I went through a lot of troubleshooting to get it to work properly considering XAMPP it's a bit buggy. I did a bunch of uninstalling, reinstalling, configuring and troubleshooting in general. I apologize but I don't have the strength to upload every screenshot of my process. What you need to know is that I installed and configured XAMPP and osTicket in the osTicket-server instance. 


I also installed a webhook in my Elasticsearch to send alerts to my osTicket. I created an API key in osTicket to put in the Elasticsearch webhook. I then set up the webhook in Elasticsearch it forced me though to activate the 30 day trial for Elasticsearch as the webhook function isn't a free feature. I did that through the private IPs of both the Elk Stack-server and the osTicket-server since they are in the same VPC network the osTicket server had the wrong public address by default but I changed it through the network properties when I rdp'ed into it.



