# ASUS H97I-PLUS Hackintosh Clover EFI
This is my Clover config for a rig running 4th gen Intel graphics and Catalina.

## PC Specs
- OS: Mac OS Catalina 10.15.7
- CPU: Intel Xeon E3-1246v3 (with Intel HD P4600 graphics)
- Motherboard: ASUS H97I-Plus
- RAM: 2x8GB DDR3 1777MHz HyperX
- SSD: 1TB Samsung EVO 960 SATA M.2 SSD
- WiFi: Dell DW1510 Half Mini-PCIe
- PCI: Firewire 800

## Additional Info
### Xeon Graphics
```config.plist``` sets Devices->IntelGFX->FakeID to ```0x04128086``` for in order to activate graphics acceleration on Catalina. This may not be necessary or may even break graphics acceleration depending on your Intel graphics.
### PCI Wifi
Getting the DW1510 to work under Catalina requires patching kexts directly into L/E. In my case, I used a Mojave kext (uploaded on this repo on the root directory) to get WiFi to work. All other kexts I tried, including ones "designed" for Catalina, usually resulted in several kernel panics. Either run the commands in a terminal or use Hackintool to patch the IO80211 kext.
