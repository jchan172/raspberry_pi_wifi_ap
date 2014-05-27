README
======

This repo contains the script `install-rt8188cus.sh` that installs and configures all the necessary tools for making a Raspberry Pi using a dongle that has a Realtek RTL8188CUS chipset into a wifi access point. I've used this along with PiUi SD card image (tutorial [here][PiUi Tutorial]). This is taken from [this blog][RTL8188 Access Point installation script] and modified to address some small gotchas (mentioned in the Notes section). Once the Raspberry Pi is set up, pull this repo down, and run

	sudo chown root:root install-rtl8188cus.sh
	sudo chmod 755 install-rtl8188cus.sh
	sudo ./install-rtl8188cus.sh

You will the be prompted for some information in order to set up the Raspberry Pi as an access point.

Note that the script will perform a fetch in order to get a compatible `hostapd` binary that is compatible with the rtl driver. If that address (http://dl.dropbox.com/u/1663660/hostapd/hostapd) ever becomes broken, the `hostapd` in this repo can be used. It was downloaded from that address.

Notes
-----

Make sure you use the correct wireless interface (e.g. wlan0, wlan1).

The `hostapd` binary will be in /usr/sbin/ after running the script. Place it into the correct directory (use `which hostapd` to find out the correct directory)

Reference
---------
[RTL8188 Access Point installation script] - source of script

[How to setup RTL8188CUS on RPi as an Access Point.] - gives some detail of what happens inside script

[PiUi Tutorial] - How to set up a mobile phone UI accessible from a Raspberry Pi

[PiUi Tutorial]: http://blog.davidsingleton.org/introducing-piui/
[RTL8188 Access Point installation script]: http://blog.sip2serve.com/post/48899893167/rtl8188-access-point-install-script
[How to setup RTL8188CUS on RPi as an Access Point.]: http://blog.sip2serve.com/post/48420162196/howto-setup-rtl8188cus-on-rpi-as-an-access-point#notes