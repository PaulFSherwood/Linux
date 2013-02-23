touch .bashrc

vim .bashrc

# .bashrc

# Source global definitions
if [ -f /etc/bashrc ]; then
	. /etc/bashrc
fi

# User specific aliases and funtions

if you run in to trouble you do the following
if your changing colors for root user
carefull with rm command you could end up removing
all file and folders on your entire system.

adduser deleteme

cp /home/deleteme/.bashrc /root/.bashrc

userdel deleteme

man need to do

rm -rvf /home/deleteme