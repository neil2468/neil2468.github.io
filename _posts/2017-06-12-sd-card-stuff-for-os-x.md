---
title:  "SD Card Stuff for OS X"
categories: ["OS X"]
---

## Determine Device Node Assigned to SD Card

Use the command `diskutil list` to determine the device node (e.g. `/dev/disk2`) assigned by OS X to the SD card. Run it once with the SD card removed and then again with the card inserted.

## Unmount SD Card

```
diskutil unmountDisk <deviceNode>
```

## Eject SD Card

```
diskutil eject <deviceNode>
```

## Write Image to SD Card

This will low-level overwrite the SD card. Don't expect to be able to access any filesystems or data that was on the SD card before the write. 

The SD card needs to be inserted but not mounted. 

To launch the write process, run the below command. The `pv` portion provides on-screen status updates while writing. For possibly faster writes, use the device node `/dev/rdiskX` in place of `/dev/diskX` (e.g. `/dev/rdisk2` rather than `/dev/disk2`). 

An error like `Invalid number '1m'` may mean `bs=1m` needs to be changed to `bs=1M`. Check your `dd` documentation.

```
sudo sh -c "dd if=<pathToImgFile> bs=1m | pv | dd of=<deviceNode> bs=1m"
```

## Zero-Erase SD Card

This will overwrite the SD card with zeros. It will destroy any filesystems and data that were on the card.

```
diskutil zeroErase <deviceNode>
```

<hr/>

### Specifics

* OS X 10.11.6

### Resources

* Writing a new Image to the Beaglebone Black ([derekmolloy.ie](http://derekmolloy.ie/write-a-new-image-to-the-beaglebone-black/))
* Why is “/dev/rdisk” about 20 times faster than “/dev/disk” in Mac OS X ([superuser.com](https://superuser.com/questions/631592/why-is-dev-rdisk-about-20-times-faster-than-dev-disk-in-mac-os-x))