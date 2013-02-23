make or download swap file i will use 1024Mb download

change start-Fedora-10.bat
from 
mem=256

to
mem=512


from 
cobd1="C:/colinux/swap.img"

to
cobd1="C:/colinux/swap_1024Mb"


boot into colinux

vim /etc/fstab

change 
LABLE=swap

to 
/dev/codb1