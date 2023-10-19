# Download Raspberry Pi OS 
- Raspberry Pi OS with desktop
- Raspberry Pi OS with desktop and recommended software
- Raspberry Pi OS Lite

        https://www.raspberrypi.com/software/operating-systems/
    
# Install Raspberry Pi OS using 
- Raspberry Pi Imager

        https://www.raspberrypi.com/software/
- Win32DiskImager

        https://sourceforge.net/projects/win32diskimager/
- BlenaEtcher

        https://etcher.balena.io/
        https://pan.baidu.com/share/init?surl=klZpn8-ubwBlFMbQ60Lo6A  | getCode: 9g5u

# Format SD
- SD Card Formatter

        https://www.sdcard.org/downloads/formatter/
- Raspberry Pi Imager >> 擦除
- Run DiskGenius

        https://www.diskgenius.com/download.php
- 计算机管理 > 存储 > 磁盘管理
    
# Install Raspberry Pi OS
1. TF card input Raspberry Pi
2. start install

# SSH Pi
- VNC

        https://www.realvnc.com/en/connect/download/viewer/
- PuTTY
        
        https://www.chiark.greenend.org.uk/~sgtatham/putty/
- Xshell

# Connect PI with WI-FI
- add file SSH with no file type under folder boot
- add file wpa_supplicant.conf under folder boot
        country=CN
        ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
        update_config=1
        
        network={
        ssid="网络名称，使用英语，保留引号"
        psk="网络密码，保留引号"
        key_mgmt=WPA-PSK
        priority=1
        } 

# Check OS Version
        cat /etc/os-release

        PRETTY_NAME="Raspbian GNU/Linux 11 (bullseye)"
        NAME="Raspbian GNU/Linux"
        VERSION_ID="11"
        VERSION="11 (bullseye)"
        VERSION_CODENAME=bullseye
        ID=raspbian
        ID_LIKE=debian
        HOME_URL="http://www.raspbian.org/"
        SUPPORT_URL="http://www.raspbian.org/RaspbianForums"
        BUG_REPORT_URL="http://www.raspbian.org/RaspbianBugs"
        
# Install DB







