# CUSTOMIZE ISO LINUX

Example for paladin7.iso

$ sudo apt-get install squashfs-tools

$ sudo mount -o loop <iso_filename> <mount_point>

$ rsync -avr <mount_point> <tmp_folder>
$ cd <tmp_folder>
$ cd casper
$ sudo su
$ unsquashfs filesystem.squashfs
$ rm filesystem.squashfs
$ chroot squashfs-root
... do the modifications at this moment (eg : change wallpaper, keyboard layout, install apps, ...)

$ exit
$ mksquashfs squashfs-root/ filesystem.squashfs -noappend -always-use-fragments
$ rm -r squashfs-root
$ cd <mount_point>
$ mkisofs -o <new_iso_filename> -b isolinux/isolinux.bin -c isolinux/boot.cat -no-emul-boot -boot-load-size 4 -boot-info-table -J -R -V "Paladin 7.0 - Police" <tmp_folder>

... to create a usb bootable 

$ ddrescue <new_iso_filename> <usb_device> --force -D
