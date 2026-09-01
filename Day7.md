I added the custom windows event logs integration to my Elasticsearch gui.

<img src="Images/Addintegrationsingestutorialday7.png">
<img src="Images/CustomwindowseventlogsDay7.png">

and more specifically I added a custom windows event log for Sysmon and for windows defender of the windows-server.
<img src="Images/AddingcustomwindowseventlogsDay7.png">
I needed the channel.
<img src="Images/windowsserverRDPfindingchannelnameDay7.png">
I found it through the event viewer and the properties of Sysmon.
<img src="Images/IntegrationPolicyDay7.png">
I added the integration to my windows-policy in Elasticsearch.

For windows defender integration I did pretty much the same thing but this time I specified 3 IDs that I would like to be specifically monitored so that our Elasticsearch isn't bogged down by millions of useless activity logs.
<img src="Images/1116idDay7.png">
<img src="Images/1117idDay7.png">
<img src="Images/5001idDay7.png">

Those are the ones I considered the most important.

<img src="Images/EventIDsDay7.png">
Here's me adding them to the windows defender integration.

<img src="Images/IntegrationPolicyDay7.png">
I added the integration to my windows-policy in Elasticsearch.

<img src="Images/ResultDay7.png">
Now I am able to view all the logs that interest me using the winlog.event_id:* term in the search bar. That's day 7. 
