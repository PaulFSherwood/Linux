echo $DISPLAY
xauth list "$DISPLAY"
su - otheruser
xauth add <output from xauth above>
export DISPLAY="<output from echo $DISPLAY>"

firefox


++++++++++++++++++++++++++++++++++++++++++++++
++++++++++++++++++++++++++++++++++++++++++++++

xhost +   (all users able to access X server, you could use also "xhost +otheruser")

su otheruser

firefox
