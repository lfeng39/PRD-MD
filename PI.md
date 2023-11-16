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

# Check PI OS Version
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

# Check Soft Sources
        > cd /etc/aapt
        > dir
        
        apt.conf.d   listchanges.conf	 preferences.d	sources.list.d	trusted.gpg~
        auth.conf.d  listchanges.conf.d  sources.list	trusted.gpg	trusted.gpg.d

        '''
        check
        '''
        > cat sources.list
        '''
        edit
        '''
        > nano sources.list

        https://wiki.diustou.com/cn//树莓派系列教程：更换软件源

# Install Python3.7.4
Download 3.7.4 tgz

        wget https://www.python.org/ftp/python/3.7.4/Python-3.7.4.tgz
Path on Pi

        /home/lfeng/Python-3.7.4
Install

        cd Python-3.7.4
        [lfeng@raspberrypi:~/Python-3.7.4 $ sudo ./configure && sudo make && sudo make install

        waitting...
        Successfully!

# Make 软连接
check 软连接

        sudo ls -a /usr/bin/ |grep python

        arm-linux-gnueabihf-python3.9-config
        arm-linux-gnueabihf-python3-config
        python
        python3
        python3.7
        python3.9
        python3.9-config
        python3-config

delete 原python软连接

        sudo rm /usr/bin/python

        arm-linux-gnueabihf-python3.9-config
        arm-linux-gnueabihf-python3-config
        --python--
        python3
        python3.7
        python3.9
        python3.9-config
        python3-config

create 软链接

        sudo ln -s /usr/local/bin/python3.7 /usr/bin/python

