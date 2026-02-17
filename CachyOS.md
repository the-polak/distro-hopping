---
title: 02-16-2026 CachyOS Post Install
date_iso: 2026-02-16
type:
  - daily
  - project
status: active
tags:
  - homelab
  - daily
  - cachyos
  - post-install
aliases:
  - 02-16-26
---


# [CachyOS Post Install](https://wiki.cachyos.org/configuration/post_install_setup/)
---
	A few things to do after installing CachyOS. I distro-hop a lot so a few reminders are extremely helpful. 

> [!NOTE]
> Trust, but verify in the [Official CachyOS Post Install Guide.](https://wiki.cachyos.org/configuration/post_install_setup/) 

<br>
<br>
## Update

[Update](https://wiki.cachyos.org/configuration/post_install_setup/#updating-the-system)
Multiple update paths exist. See the [official CachyOS post-install guide.](https://wiki.cachyos.org/configuration/post_install_setup/#updating-the-system)

```bash
	sudo pacman -Syu
```
<br>
<br>

## [Wi-Fi Regulatory Domain](https://wiki.cachyos.org/configuration/post_install_setup/#configure-wi-fi-regulatory-domain)

Edit `sudo micro /etc/conf.d/wireless-regdom`, uncomment applicable `#WIRELESS_REGDOM="XXXXXXXXX"`

```bash
sudo micro /etc/conf.d/wireless-regdom
```
![700](assets/2026-02-16_4.png)
### `WIRELESS_REGDOM="US"` Confirmation
```bash
❯ iw reg get  
global  
country 00: DFS-UNSET  
       (755 - 928 @ 2), (N/A, 20), (N/A), PASSIVE-SCAN  
       (2402 - 2472 @ 40), (N/A, 20), (N/A)  
       (2457 - 2482 @ 20), (N/A, 20), (N/A), AUTO-BW, PASSIVE-SCAN  
       (2474 - 2494 @ 20), (N/A, 20), (N/A), NO-OFDM, PASSIVE-SCAN  
       (5170 - 5250 @ 80), (N/A, 20), (N/A), AUTO-BW, PASSIVE-SCAN  
       (5250 - 5330 @ 80), (N/A, 20), (0 ms), DFS, AUTO-BW, PASSIVE-SCAN  
       (5490 - 5730 @ 160), (N/A, 20), (0 ms), DFS, PASSIVE-SCAN  
       (5735 - 5835 @ 80), (N/A, 20), (N/A), PASSIVE-SCAN  
       (57240 - 63720 @ 2160), (N/A, 0), (N/A)  
  
phy#0 (self-managed)  
country US: DFS-UNSET  
       (2402 - 2437 @ 40), (6, 22), (N/A), AUTO-BW, NO-HT40MINUS, NO-80MHZ, NO-160MHZ  
       (2422 - 2462 @ 40), (6, 22), (N/A), AUTO-BW, NO-80MHZ, NO-160MHZ  
       (2447 - 2482 @ 40), (6, 22), (N/A), AUTO-BW, NO-HT40PLUS, NO-80MHZ, NO-160MHZ  
       (5170 - 5190 @ 160), (6, 22), (N/A), AUTO-BW, NO-HT40MINUS, NO-320MHZ  
       (5190 - 5210 @ 160), (6, 22), (N/A), AUTO-BW, NO-HT40PLUS, NO-320MHZ  
       (5210 - 5230 @ 160), (6, 22), (N/A), AUTO-BW, NO-HT40MINUS, NO-320MHZ  
       (5230 - 5250 @ 160), (6, 22), (N/A), AUTO-BW, NO-HT40PLUS, NO-320MHZ  
       (5250 - 5270 @ 160), (6, 22), (0 ms), DFS, AUTO-BW, NO-HT40MINUS, NO-320MHZ, PASSIVE-SCAN  
       (5270 - 5290 @ 160), (6, 22), (0 ms), DFS, AUTO-BW, NO-HT40PLUS, NO-320MHZ, PASSIVE-SCAN  
       (5290 - 5310 @ 160), (6, 22), (0 ms), DFS, AUTO-BW, NO-HT40MINUS, NO-320MHZ, PASSIVE-SCAN  
       (5310 - 5330 @ 160), (6, 22), (0 ms), DFS, AUTO-BW, NO-HT40PLUS, NO-320MHZ, PASSIVE-SCAN  
       (5490 - 5510 @ 160), (6, 22), (0 ms), DFS, AUTO-BW, NO-HT40MINUS, NO-320MHZ, PASSIVE-SCAN  
       (5510 - 5530 @ 160), (6, 22), (0 ms), DFS, AUTO-BW, NO-HT40PLUS, NO-320MHZ, PASSIVE-SCAN  
       (5530 - 5550 @ 160), (6, 22), (0 ms), DFS, AUTO-BW, NO-HT40MINUS, NO-320MHZ, PASSIVE-SCAN  
       (5550 - 5570 @ 160), (6, 22), (0 ms), DFS, AUTO-BW, NO-HT40PLUS, NO-320MHZ, PASSIVE-SCAN  
       (5570 - 5590 @ 160), (6, 22), (0 ms), DFS, AUTO-BW, NO-HT40MINUS, NO-320MHZ, PASSIVE-SCAN  
       (5590 - 5610 @ 160), (6, 22), (0 ms), DFS, AUTO-BW, NO-HT40PLUS, NO-320MHZ, PASSIVE-SCAN  
       (5610 - 5630 @ 160), (6, 22), (0 ms), DFS, AUTO-BW, NO-HT40MINUS, NO-320MHZ, PASSIVE-SCAN  
       (5630 - 5650 @ 160), (6, 22), (0 ms), DFS, AUTO-BW, NO-HT40PLUS, NO-320MHZ, PASSIVE-SCAN  
       (5650 - 5670 @ 80), (6, 22), (0 ms), DFS, AUTO-BW, NO-HT40MINUS, NO-160MHZ, NO-320MHZ, PASSIVE-SCAN  
       (5670 - 5690 @ 80), (6, 22), (0 ms), DFS, AUTO-BW, NO-HT40PLUS, NO-160MHZ, NO-320MHZ, PASSIVE-SCAN  
       (5690 - 5710 @ 80), (6, 22), (0 ms), DFS, AUTO-BW, NO-HT40MINUS, NO-160MHZ, NO-320MHZ, PASSIVE-SCAN  
       (5710 - 5730 @ 80), (6, 22), (0 ms), DFS, AUTO-BW, NO-HT40PLUS, NO-160MHZ, NO-320MHZ, PASSIVE-SCAN  
       (5735 - 5755 @ 80), (6, 22), (N/A), AUTO-BW, NO-HT40MINUS, NO-160MHZ, NO-320MHZ  
       (5755 - 5775 @ 80), (6, 22), (N/A), AUTO-BW, NO-HT40PLUS, NO-160MHZ, NO-320MHZ  
       (5775 - 5795 @ 80), (6, 22), (N/A), AUTO-BW, NO-HT40MINUS, NO-160MHZ, NO-320MHZ  
       (5795 - 5815 @ 80), (6, 22), (N/A), AUTO-BW, NO-HT40PLUS, NO-160MHZ, NO-320MHZ  
       (5815 - 5835 @ 20), (6, 22), (N/A), AUTO-BW, NO-HT40MINUS, NO-HT40PLUS, NO-80MHZ, NO-160MHZ, NO-320MHZ
```
<br>
<br>

## [AppImages](https://wiki.cachyos.org/configuration/post_install_setup/#managing-appimages)
```bash
# install #FUSE
sudo pacman -S fuse2

# Install AppImageLauncher
paru appimagelauncher

# Make executable
chmod +x /home/kielbasa/Applications/app-here
```




## Apps
Applications for my daily driver. 

### Install with Octopi, `pacman -Ss appname` or  AppImage. 

- Alacritty
- Brave
- btop
- Floorp Browser
- ethtool
- Glances
- gparted
- Mailspring
- Obsidian
- Rofi # new
- Signal
- Telegram
- Visual Studio Code (non-free)
	- <mark style="background:rgba(3, 135, 102, 0.2)">*Yeah, really.* </mark>

### App Install Script
See also: [02-17-2026 CachyOS app install script](02-17-2026%20CachyOS%20app%20install%20script.md) or git clone here XxXxX
<br>
<br>

# Sources
- https://wiki.cachyos.org/configuration/post_install_setup
- https://wiki.cachyos.org/cachyos_basic/faq/#security--best-practices


