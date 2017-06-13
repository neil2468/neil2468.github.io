---
title: OS X Screen and USB to Serial
categories: ["os x"]
---

## Contents
{: .no_toc}
* TOC 
{:toc}
<hr/>

Assuming the USB to serial converter has been assigned the device node `/dev/cu.SLAB_USBtoUART` and your connection is 115200 baud, use the below command to launch screen.

```
screen /dev/cu.SLAB_USBtoUART 115200
```

## Screen Shortcuts

Screen is a terminal emulator so naturally it will ignore and pass on our keystrokes to the connected device. So how do we interact with screen? Using `^a`.

Keystrokes | Action
---------- | ------
^a ?       | Display help
^a ^\      | Quit

## .screenrc

It seems screen will configure itself from a `.screenrc` file in your home directory. See [slaptijack.com](http://slaptijack.com/system-administration/mac-os-x-terminal-and-gnu-screen-scrollback/).

<hr/>

## Specifics & Resources

* MacBook Pro connected to a BeagleBone Black's 3.3v UART0 via a USB to UART converter
* CP2104 Serial Converter USB 2.0 to TTL UART 6PIN (CNT-003B, cnewtec.com)
* OS X 10.11.6





 


