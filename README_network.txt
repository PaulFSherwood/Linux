WINDOWS
IP address:		192.168.137.1

Subnet mask:		255.255.0.0

Default gateway:	...


Preferred DNS server:	...


COLINUX
IP address:		192.168.137.102

Subnet mask:		255.255.0.0

Default gateway:	...


Preferred DNS server:	...



NOTWORKING....
IP address:		192.168.1.200

Subnet mask:		255.255.255.0

Default gateway:	192.168.1.1


Preferred DNS server:	192.168.1.1



					   -------------------------
					   |			   |
				       ----|			   |
		-------------------    |   |	colinux		   |
		|		  |    |   |			   |
		|		  |-----   |			   |
       cat 5 ---|		  |	   -------------------------
		|   bridge	  |	   
		|		  |        -------------------------
		|		  |-----   |			   |
		|		  |    |   |			   |
		-------------------    |   |	windows 	   |
				       ----|			   |
					   |			   |
					   -------------------------


THE FOLLOWING SETTING MAY BE WRONG

WINDOWS
IP address:		192.168.137.1

Subnet mask:		255.255.255.0

Default gateway:	192.168.137.101(doesnt work tho)


Preferred DNS server:	97.64.180.150
			97.64.179.254



stable settings
     ==================================
WINDOWS
Local Area Connection 2
IP address:		192.168.137.1

Subnet mask:		255.255.255.0

Default gateway:	...
Preferred DNS server:	97.64.180.150
			97.64.179.254

     ==================================
Local Area Connection
IP address:		173.18.181.221

Subnet mask:		255.255.248.0
Default gateway:	173.18.176.1
DHCP Server		97.64.180.224


Preferred DNS server:	97.64.180.150
			97.64.179.254


     ==================================
COLINUX
IP address:		192.168.137.247
Bcast:			192.168.137.255

Subnet mask:		255.255.255.0

Default gateway:	...


Preferred DNS server:	...

     ==================================