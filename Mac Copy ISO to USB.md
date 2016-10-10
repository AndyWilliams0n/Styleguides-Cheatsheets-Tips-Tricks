# Mac Cheatsheet

## Copy ISO to USB using mac terminal

| Command | Description |
| ------- | ----------- |
| 1 > diskutil list | List mounted HD's and USB Sticks |
| 2 > sudo diskutil unmount /dev/my-usb-stick | Unmounts the USB stick you wish to become imaged, i.e. sudo diskutil unmount /dev/disk2s1 |
| 3 > sudo dd if=/path-to.iso of=/dev/my-usb-stick bs=1m | Copy the ISO to your USB stick, i.e. sudo dd if=/Users/me/Desktop/Windows10x64.iso of=/dev/rdisk2s1 bs=1m |

Please note, this does take some time to copy, please wait for this message: X bytes transferred in X secs (X bytes/sec)

| 4 > diskutil eject /dev/my-usb-stick | Eject your USB disk, i.e. diskutil eject /dev/disk2s1 |

Done