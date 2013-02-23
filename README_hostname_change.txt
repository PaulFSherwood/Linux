http://www.xenocafe.com/tutorials/linux/redhat/change_hostname_without_reboot/index.php
# 
# cd /etc/sysconfig
# vi network
# 


Look for the HOSTNAME line and replace it with the new hostname you want to use. In this example I want to replace localhost with redhat9.

# 
# HOSTNAME=redhat9
# 


When you are done, save your changes and exit vi. Next we will edit the /etc/hosts file and set the new hostname.

# 
# vi /etc/hosts
# 


In hosts, edit the line that has the old hostname and replace it with your new one.
# 
# 192.168.1.110		redhat9
# 

Save your changes and exit vi. The changes to /etc/hosts and /etc/sysconfig/network are necessary to make your changes persistent (in the event of an unscheduled reboot).

Now we use the hostname program to change the hostname that is currently set.

# 
# hostname redhat9
# 

And run it again without any parameters to see if the hostname changed.

# 
# hostname
# 


Finally we will restart the network to apply the changes we made to /etc/hosts and /etc/sysconfig/network.

# 
# service network restart
# 


To verify the hostname has been fully changed, logout of your system and you should see your new hostname being used at the login prompt and after you've logged back in.