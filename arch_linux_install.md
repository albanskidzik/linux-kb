
link: https://github.com/manilarome/A-Personal-Arch-Installation-Guide


* Keyboard layout

ls /usr/share/kbd/keymaps/**/*.map.gz
loadkeys pl
ls /usr/share/kbd/consolefonts/
setfont Lat2-Terminus16.psfu.gz -m 8859-2

* Sprawdzić czy system jest w trybie uefi. Sprawdzić zawartość katalogu

ls /sys/firmware/efi/efivars

* Sprawdzić połączenie z internetem

ip link

ping archlinux.org
ls

* Synchronizacja czasu

timedatectl set-ntp true

* Partycjonowanie dysku

fdisk -l

efi - 500M, swap 32GB, reszta na jednej partycji


mkfs.ext4 /dev/nvme0n1p3
mkswap /dev/nvme0n1p2
swapon /dev/nvme0n1p2

mount /mnt /dev/nvme0n1p3



pacstrap /mnt base linux linux-firmware







After grub install

cd /mnt/boot/EFI/EFI/
mkdir /BOOT
cp GRUB/grubx64.efi /BOOT/GRUBX64.EFI

cd /mnt/boot/efi - mount point
na partycji EFI
edit starutup.nsh

bcf boot add 1 fs0:\EFI\grub_uefi\grubx64.efi "My grub bootloader"
exit





