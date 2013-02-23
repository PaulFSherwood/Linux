http://colinux.wikia.com/wiki/Sound_support_in_Colinux

WINDOWS SIDE:::::

http://www.cendio.com/pulseaudio/pulseaudio-0.9.6-1.win32.zip

extract to 
C:/colinux/pulseaudio-0.9.6/

cd C:/colinux/pulseaudio-0.9.6/ && touch default.pa && notepad.exe default.pa

CODE

load-module module-native-protocol-tcp auth-ip-acl=127.0.0.1;192.168.0.0/16
load-module module-esound-protocol-tcp auth-ip-acl=127.0.0.1;192.168.0.0/16
load-module module-detect

CODE

********************************************************************************
********************************************************************************
cd C:/colinux/pulseaudio-0.9.6/ && touch daemon.conf && notepad.exe daemon.conf

CODE

# daemonize appears to not work under Windows 
 # other than to ignore SIGINT 
 daemonize=0
 dl-search-path=C:\coLinux\pulseaudio-0.9.6
 fail=0 
 high-priority=1 
 use-pid-file=0

CODE

********************************************************************************
********************************************************************************

cd C:/colinux/ && notepad.exe start-Fedora-10.bat

add

CODE

 exec0="C:/colinux/pulseaudio-0.9.6/pulseaudio.exe"

CODE

ipconfig /all 
find your ipv4(for me) ip address example 192.168.137.1

********************************************************************************
********************************************************************************

COLINUX:::::

ls /etc | grep pulse

if pulse dir is there

cp /etc/pulse/client.conf /etc/pulse/client.conf.bak
vim /etc/pulse/client.conf

uncomment default-server = 
add 
CODE

defalut-server = 192.168.137.1

CODE

////////////////////////////////////////////////////////////////////////////////
\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\

mine failed and had to 
1. edit C:\coLinux\pulseaudio-0.9.6\default.pa
CODE
load-module module-native-protocol-tcp listen=0.0.0.0
load-module module-waveout


2. cp C:\Documents and Settings\grrwood\.pulse-cookie to LINUX ~/
3. daemon.conf renamed to daemon.conf_bak ((to not be used))

////////////////////////////////////////////////////////////////////////////////
\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\

changed 
C:\coLinux\pulseaudio-0.9.6\default.pa
CODE 
load-module module-native-protocol-tcp auth-ip-acl=127.0.0.1;192.168.0.0/16
load-module module-esound-protocol-tcp auth-ip-acl=127.0.0.1;192.168.0.0/16
load-module module-detect


ok working now the problem was in security of pulseaudio

////////////////////////////////////////////////////////////////////////////////
\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\

Vlc would not play music now pulseaudio denied access on windows side.

changed 
C:\coLinux\pulseaudio-0.9.6\default.pa
CODE 
load-module module-native-protocol-tcp auth-anonymous=1
load-module module-esound-protocol-tcp auth-anonymous=1
load-module module-detect

////////////////////////////////////////////////////////////////////////////////
\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\

Audio issue no sound or no mic

::check to see if any audio service is running
pulseaudo --check
=====
::kill pulseaudio if its running
pulseaudio -k
=====
::start pulseaudio again
pulseaudio -D
