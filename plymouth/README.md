The directory "cometvisu" should be copyed on the system to the directory 
for the plymouth themes.
* On Ubuntu (14.04) this is: /lib/plymouth/themes/
* On Ubuntu (16.04) this is: /usr/share/plymouth/themes/

When update-alternatives is used (like on Ubuntu) then this alternative
should be announced to the system. This can be done with: 

update-alternatives --install /lib/plymouth/themes/default.plymouth default.plymouth /lib/plymouth/themes/cometvisu/cometvisu.plymouth 100

By running

update-alternatives --config default.plymouth

it can be made sure that this theme is the chosen one.

To activate it during system start the intiram must be recreated. For the
current kernel this is done with

update-initramfs -u

(For all kernels you can use update-initramfs -u -k all)

Now the CometVisu theme should run during each startup. When only a text
theme is shown, please debug that startup procedure itself.
