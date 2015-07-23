From https://amalgjose.wordpress.com/tag/raspbian/

To make this working, we have to do some modifications.
Add the following contents to the /etc/rc.local file

sudo pico /etc/rc.local

modprobe 8192cu
echo "0846 9043" > /sys/bus/usb/drivers/rtl8192cu/new_id
ifdown wlan0
ifup wlan0

Then add the following contents to /etc/modprobe.d/netgear_n150.conf file

sudo pico /etc/modprobe.d/netgear_n150.conf
install 8192cu /sbin/modprobe --ignore-install 8192cu; echo "0846 9043" > /sys/bus/usb/drivers/rtl8