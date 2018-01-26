# How to install Arch Linux

<p align="center">
  <img src="http://www.hisense.es/blog/wp-content/uploads/2017/10/Netflix-octubre-2017.jpg" width="250">
</p>

## Download an Arch iso

## Run Arch cd
1. Select Boot Arch Linux

### Part One - Partitioing the Hard Drive
```sh
#See your disk
$ fdisk -l 
# Run a partition manager
$ cfdisk /dev/sda
# If Arch is the only operativo system, delete all the partitions
# Create a swap partition
## New - Partition primary - Select the size as you want
## Select type - Linux Swap
# With the rest of the space - Select new - Select Bootable
# And now select write and quit
$ mkfs.ext4 /dev/sda2
$ mount /dev/sda2 /mnt
# We are going to create a swap file in the swap partition
$ mkswap /dev/sda1
$ swapon /dev/sda1
```

### Part Two - Installing the system
```sh
# You need an internet connection
# We are going to install in the root partition
$ pacstrap /mnt base base-devel
# Wait some time
```

### Part Three - Configuring the installation
```sh
# Create an chroot
$ arch-chroot /mnt
$ nano /etc/locale.gen
# Select your lenguage and uncomment
$ locale-gen
# now we are going to select our timezone
$ cd /usr/share/zoneinfo
# Select yours (Europe)
$ cd /usr/share/zoneinfo/Europe
$ ln -s /usr/share/zoneinfo/Europe/Madrid /etc/localtime
# Put the name of your hostname
$ echo loritobonito > /etc/hostname
# Install grub
$ pacman -Syu
$ pacman -S grub-bios
$ grub-install /dev/sda
# Create the image
$ mkinitcpio -p linux
$ grub-mkconfig -o /boot/grub/grub.conf
# exit the chroot sesion
$ exit
$ genfstab /mnt >> /mnt/etc/fstab
$ umount /mnt 
$ reboot
```
