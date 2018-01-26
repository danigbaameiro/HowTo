# How to install Arch Linux

<p align="center">
  <img src="https://www.linuxadictos.com/wp-content/uploads/arch-linux-logo.jpg" width="250">
</p>

## Download an Arch iso

## Run Arch cd
1. Select Boot Arch Linux

### Part One - Partitioing the Hard Drive
```sh
# Set spanish landguage
$ loadkeys es
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
# update the keys
$ pacman -Sy archlinux-keyring
# We are going to install in the root partition
$ pacstrap /mnt base base-devel grub-bios networkmanager
# If we have a touchpad
$ pacstrap /mnt xf86-input-synaptics
# Wait some time
$ genfstab -U -p /mnt >> /mnt/etc/fstab
```

### Part Three - Configuring the installation
```sh
# Create an chroot
$ arch-chroot /mnt
$ nano /etc/locale.gen
# Select your lenguage and uncomment
$ locale-gen
# Location preferences
$ nano /etc/locale.conf 
# Write LANG=es_ES.UTF-8
# now we are going to select our timezone
$ cd /usr/share/zoneinfo
# Select yours (Europe)
$ cd /usr/share/zoneinfo/Europe
$ ln -s /usr/share/zoneinfo/Europe/Madrid /etc/localtime
# Put the name of your hostname
$ echo loritobonito > /etc/hostname
# Distribution keyboard
$ nano /etc/vconsole.conf
# Write KEYMAP=es
# Install grub
$ grub-install /dev/sda
# Create the fike
$ grub-mkconfig -o /boot/grub/grub.conf
# Create the image
$ mkinitcpio -p linux
# Set the root password
$ passwd
# exit the chroot sesion
$ exit
$ umount /mnt 
$ reboot
```

### Part Four - Creating users
```sh
# Change sawyer for your user
$ useradd -m -g users -G audio,lp,optical,storage,video,wheel,games,power,scanner -s /bin/bash sawyer
# Password for your user
$ passwd sawyer
# Now edit sudoers file
$ nano /etc/sudoers
# Uncomment %wheel ALL=(ALL) ALL
# And now reboot
$ reboot
$ sudo pacman -Syu
```

### Part Five - Graphic environment
#### KDE
```sh
$ sudo pacman -S kde
#Install complements
## Spanish language
$ sudo pacman -S kde-l10n-es
## NetworkManager support
$ sudo pacman -S kdeplasma-applets-plasma-nm
# Package manager
$ sudo pacman -S apper
# Install KDM
$ sudo systemctl enable kdm.service
# And now reboot
$ sudo reboot
```

#### Gnome
```sh
$ sudo pacman -S gnome gnome-extra
# Install complements
## Battery applet
$ sudo pacman -S gnome-power-manager
## Gnome-tweak-tool
$ sudo pacman -S gnome-tweak-tool
## GDM
$ sudo systemctl enable gdm.service
$ sudo reboot
```
