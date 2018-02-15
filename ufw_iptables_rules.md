https://www.cyberciti.biz/faq/howto-limiting-ssh-connections-with-ufw-on-ubuntu-debian/

https://help.ubuntu.com/community/IptablesHowTo

https://stackoverflow.com/questions/10197405/how-can-i-remove-specific-rules-from-iptables


//list all iptables rules
iptables -S
iptables -L INPUT --line-numbers  
  

-A	ADD  
-D	DELETE  
-F	DROP ALL RULES  
  

  
networkctl