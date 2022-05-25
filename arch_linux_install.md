
1. Keyboard layout
ls /usr/share/kbd/keymaps/**/*.map.gz
loadkeys pl
ls /usr/share/kbd/consolefonts/
setfont Lat2-Terminus16.psfu.gz -m 8859-2

After grub install

cd /mnt/boot/EFI/EFI/
mkdir /BOOT
cp GRUB/grubx64.efi /BOOT/GRUBX64.EFI

cd /mnt/boot/EFI
edit starutup.ns ???

