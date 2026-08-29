I set up kibana very similarly to elasticsearch, copy paste link from download website use wget and dpkg -i to download and install it.


Set a new firewall group from vultr to **allow in every TCP port from 1:65535** that comes from **my public IP ONLY**, I did not open every port to the internet. 


Configured the kibana.yml file to use the **5601 port** that it needs and set the localhost IP to the server's public IP. 


I accessed the elastic gui via web browser after using **ufw allow 5601** on the ubuntu server because I needed to auth the port from inside the server too. 


In the web gui I **logged in with the username and password** given to me when setting up Elasticsearch from the **Security autoconfiguration information**. 


Then it asked for a **verification code from the kibana-verification-code.bat file**. I run it from inside the machine and it gave me a 6 digit code to authenticate myself with. 


Lastly I **set up kibana's encryption keys** by generating them using **./kibana-encryption-keys generate** in turn it gave me 3 keys which I had to **insert to the kibana keystore** using **./kibana-keystore add (Name of key) (Key)**.

The names of the keys, keys ommited

xpack.encryptedSavedObjects.encryptionKey

xpack.reporting.encryptionKey

xpack.security.encryptionKey

