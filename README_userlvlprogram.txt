quick script to run program as diffirent users

# $vi sayH
#
#Script to run user mode
#
xhost +
echo "username: "
read fuser
echo "user $fuser"
echo "program name: "
read fprog
echo "starting $fprog"
echo "kdesu -u $fuser $fprog &"
kdesu -u $fuser $fprog &

# tried with sudo -u $fuser $fprog &
# however it would take to long to load
# and there where problems with Xwin