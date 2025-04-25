# mikrotik
Cyber Threat Intel for Mikrotik routers in RSC format 
#### Script contributed by JayR Baldeva
#### This is assuming you download the WatchDogBlocklist.rsc to your desktop first
#### and name it as WatchDogBlocklist
/import file-name=WatchDogBlocklist-current.rsc


/ip firewall filter

add action=drop chain=forward connection-state=new log-prefix=blocklist src-address-list=WatchDogBlocklist

add action=drop chain=input connection-state=new log-prefix=blocklist src-address-list=WatchDogBlocklist
