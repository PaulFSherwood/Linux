Copy whole filesystem into new image

A backup of your current running system will be the old file later. So, you not need an extra backup here.

For this steps

   1. From windows, create a blank file of the new size. For 5GB=5*1024*1024*1024 bytes, open a command prompt and run fsutil file createnew C:\??? 5368709120. (If you do not have fsutil, see HowtoCreateSwapFile.)
   2. Edit the colinux configuration file to add the blank file as a new device, for example cobd1=New.img, and restart colinux.
   3. If you can, switch into single user runlevel. init s (or shutdown now)
   4. Format filesystem. mkfs.ext3 /dev/cobd1
   5. Mount it. mkdir /tmp/mnt; mount /dev/cobd1 /tmp/mnt
      (Do not mount it on mnt: the cp -x would not work there)
   6. Copy contents to new device. cp -ax / /tmp/mnt
   7. Copy device nodes (only if udev system, i.e. kernel 2.6+). if [ -d /dev/.udev ]; then cp -a /dev/* /tmp/mnt/dev/; fi  
   8. Check that the file /tmp/mnt/etc/fstab does not have 'labels'. Use only /dev/cobd... there.
   9. Check the used sizes with df
  10. Let's sync data, a saver step for some systems. sync
  11. Unmount new device. umount /dev/cobd1
  12. Shuting down coLinux. shutdown -h now
  13. From windows, edit your config file again. Change the entry of the old device to use the newly created file. Then remove the entry created above.
  14. Restart coLinux. 

Keep the old file until you are sure the new one works! 