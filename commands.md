#check disk speed

sudo hdparm -Tt /dev/sda

/dev/sda:
Timing cached reads:   12540 MB in  2.00 seconds = 6277.67 MB/sec
Timing buffered disk reads: 234 MB in  3.00 seconds =  77.98 MB/sec

hdparm -I /dev/sda | grep -i speed


#swap priority
sudo swapon -p 10 /dev/sdb
sudo swapon -p 5  /dev/sdc

In /etc/fstab, you would pass the pri option to set the priority, like so:

/dev/sda none swap defaults,pri=10 0 0
/dev/sdb none swap defaults,pri=5  0 0


update-initramfs -uk all


swapon -s
Filename                Type        Size    Used    Priority
/dev/zd16                               partition   8388604 0   -1
/dev/zram0                              partition   1524800 275252  5
/dev/zram1                              partition   1524800 275400  5
/dev/zram2                              partition   1524800 276296  5
/dev/zram3                              partition   1524800 275392  5


sysctl vm.swappiness=99

cat /proc/sys/vm/swappiness

swapon -s


/etc/sysctl.conf
Just put vm.swappiness=10 into your /etc/sysctl.conf. On very low end hardware use vm.swappiness=1. Don't forget to reboot after the change.


free -tm


#read swap online
cat /dev/sdb | strings


#EXIF
identify -verbose /usr/share/backgrounds/WildWheat_by_Brian_Burt.jpg


# install exiftool
sudo apt-cache install libimage-exiftool-perl

# show metadata of a image file
exiftool myPhoto.jpg

# show metedata for all *jpg files in current dir
exiftool -ext jpg

# show metedata for all *jpg files in current dir and subdirs
exiftool -r -ext jpg .



# remove all metadata of a image file
exiftool -all= -overwrite_original photo.jpg

# remove all metadata of all *jpg files in current dir
exiftool -all= -overwrite_original -ext jpg .

# remove metedata for all *jpg files in current dir and subdirs
exiftool -all= -r -overwrite_original -ext jpg .


# remove all GPS metadata of *jpg files in current dir
exiftool -gps:all= *.jpg



### find
https://www.digitalocean.com/community/tutorials/how-to-use-find-and-locate-to-search-for-files-on-a-linux-vps




https://access.redhat.com/articles/1196333

https://askubuntu.com/questions/103915/how-do-i-configure-swappiness

https://superuser.com/questions/1168963/is-distributing-load-in-a-balanced-way-between-swap-partitions-possible/1168991

https://askubuntu.com/questions/432836/how-can-i-check-disk-space-used-in-a-partition-using-the-terminal-in-ubuntu-12-0/432842