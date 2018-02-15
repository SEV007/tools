ls /etc/rc*.d	//list all startup services  
  
update-rc.d -f avahi_daemon disable	//remove service from startup  
  
update-rc.d avahi-daemon defaults	//restore disabled service from startup  
  
  
service --status-all  
  
  
systemctl -l 	//list all system services  
  
search service with /  
and copy the name  
  
systemctl disable service.name	//disable the service  
  
systemctl mask	service.name	//more powerful than disable  
  
vim /etc/default/avahi-daemon	//change parameter to 0  
  
  
  
# Console GUI service manager
aptitude install rcconf sysv-rc-conf