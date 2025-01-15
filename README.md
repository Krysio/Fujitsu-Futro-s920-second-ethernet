# Fujitsu Futro s920 second ethernet connector

![Fujitsu Futro s920, the second ethernet connector](./result.jpg?raw=true "Fujitsu Futro s920, the second ethernet connector")

The Fujitsu Futro S920 motherboard is a variant of the Fujitsu D3313 motherboard, which includes a version with two 1Gb/s Ethernet ports.
The processors in the S920 have an active PCIe lane connected to the paths for the second Ethernet port. It is sufficient to solder the missing components, sourced from a damaged S920 or S720. Operating systems and BIOS will detect two Ethernet controllers without any software modifications.

Tested with:
 - s920, AMD GX-415GA SOC
 - s920, AMD GX-222GC SOC

 ## Modification

 ![Soldering the missing components on top surface](./top.jpg?raw=true "Soldering the missing components on top surface")
 ![Soldering the missing components on bottom surface](./bottom.jpg?raw=true "Soldering the missing components on bottom surface")
 ![An example modification](./2xRTL8111GSF.jpg?raw=true "An example modification")

Remember that the controller must be soldered perfectly. If soldered incorrectly, it may not be detected by the system or might connect at a speed of 100Mbps.

 ## Result

```bash
root@OpenWrt:~# lspci | grep Ethernet
01:00.0 Ethernet controller: Realtek Semiconductor Co., Ltd. RTL8111/8168/8211/8411 PCI Express Gigabit Ethernet Controller (rev 0c)
02:00.0 Ethernet controller: Realtek Semiconductor Co., Ltd. RTL8111/8168/8211/8411 PCI Express Gigabit Ethernet Controller (rev 0c)
```

## See also
[Fujitsu Futro PoE Module Pinout](https://github.com/Krysio/Fujitsu-Futro-PoE)

## License
This project is licensed under the MIT License. Feel free to use and modify the content.