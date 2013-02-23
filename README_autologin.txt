http://www.linuxquestions.org/questions/linux-newbie-8/auto-login-to-bash-721344/

lolz... simple solution found in 'man mingetty'. changed

In the "/etc/event.d/tty1"   file


change 

"exec /sbin/mingetty tty1"

to

"exec /sbin/mingetty --autologin root tty1"


BTW. in F10, /etc/inittab contains

# Terminal gettys (tty[1-6]) are handled by /etc/event.d/tty[1-6] and
# /etc/event.d/serial

so... yeah... thanks though!