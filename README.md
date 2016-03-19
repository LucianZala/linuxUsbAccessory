Use libusb to emulate usb android open accesory

@note:
If you are on Ubuntu you will require libusb as well as the headers...
sudo apt-get source libusb
sudo apt-get install libusb-dev
sudo apt-get install libusb-1.0-0-dev

Add udev rules to /etc/udev/rules.d/51-android.rules:
SUBSYSTEM=="usb", ATTR{idVendor}=="1004", MODE="0666", GROUP="plugdev"
SUBSYSTEM=="usb", ATTR{idVendor}=="18d1", MODE="0666", GROUP="plugdev" 
sudo chmod a+r /etc/udev/rules.d/51-android.rules
 
@based on:
http://android.serverbox.ch/?p=262
