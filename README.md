

# Hackintosh - macOS Big Sur - Beta 2 (20A4300b) - Z370 + 8700K + RX 580
![SystemInfo](https://raw.githubusercontent.com/huongdp/Hackintosh/master/Screenshot/BigSur/Overview.png)

# ⚠️ Disclaimer
OpenCore bootloader is currently unable to start the installation (USB installer, .etc).
The solution is to use a virtual machine and use a physical disk (additional, USB or SATA, NVME) as a target in the installation.

# Hardware

- CPU: Intel(R) CPU Core i7 8700K
- Mainboard: Gigabyte Z370 D3H
- RAM: G.SKILL Trident Z RGB 16GB 3000MHz DDR4 (8GBx4) 
- SSD:
    - Samsung SSD 970 EVO 500GB
    - Samsung SSD 970 EVO Plus 500GB
    - Seagate Barracuda 2TB 3.5" SATA (ST2000DM008)
- Wireless: Broadcom BCM943602CS  802.11ac + Bluetooth 4.1
- VGA:
  - Intel HD Graphics 630 (Onboard)
  - SAPPHIRE PULSE RX 580 8G GDDR5
- Monitors:
  - LG 27 inches 4K (3840x2160/60Hz)
  - Dell 24 inches FullHD (1920x1080/60Hz)
- Power: Corsair RM 750X 80+
- Mouse: Logitech MX Master 2S (Bluetooth or Unifying receiver)
- Keyboard: Keychron K2 Wireless Mechanical Keyboard
  
# Installation
  [INSTALLATION](INSTALLATION.md)

# BIOS
 BIOS version: [F10](https://www.gigabyte.com/Motherboard/Z370M-D3H-rev-10/support#support-dl-bios)

# What works
 - Intel HD Graphics 630 (Support Intel Quick Sync Video)
 - RX 580 AMD GPU
 - Ethernet + Wireless + Bluetooth
 - USB 2.0/3.0 Ports
 - Sleep / Wake up
 - Sounds
 - Others (updating...)
# Benchmarks
## **Normal (4.7GHz)**

OS                    | CPU (Single-Core) | CPU (Multi-Cores) | OpenCL (KBL Graphics) | OpenCL (RX 580)
----------------------|:-----------------:|:-----------------:|:------------------:|:-------:
Big Sur (Geekbench 5) |throttling|throttling|[5409](1211633)|[44622](1211665)
Big Sur (Geekbench 4) |[6250](15630067)|[30135](15630067)|[24261](4863112)|[140718](4863107)
Catalina (Geekbench 5)|[1198](2932351)|[6233](2932351)|[5450](1211793)|[43108](1211263)
Catalina (Geekbench 4)|[6231](15629857)|[30069](15629857)|[24481](4863075)|[141787](4863077)

  \**Geekbench Browser* [here](https://browser.geekbench.com/v4/cpu/15630067)

## **Overclocking (5GHz)**

  Waiting... for upgrading radiator system :)

# Credits
- Bootloaders + Kexts:
  - [OpenCore](https://github.com/acidanthera/OpenCorePkg)
  - [Acidanthera](https://github.com/acidanthera/OpenCorePkg)
- Forums
  - [dortania](https://dortania.github.io/OpenCore-Desktop-Guide)
  - [tonymacx86](https://www.tonymacx86.com)
  - [r/hackintosh](https://www.reddit.com/r/hackintosh)
