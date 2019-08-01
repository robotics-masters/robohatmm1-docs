# 树莓派驴子车安装步骤

![树莓派驴子车](/assets/logos/rpi_logo.png)

* [步骤 1: 安装系统](#1)
* [步骤 2: 初始化设置-WiFi](#2-wifi)
* [步骤 3: 初始化设置-树莓派的主机名称](#3-)
* [步骤 4: 开启SSH](#4-ssh)
* [步骤 5: 与树莓派建立连接](#5)
* [步骤 6: 升级树莓派系统套件](#6)
* [步骤 7: Raspi-config树莓派系统设置](#7-raspi-config)
* [步骤 8: 安装依赖软件包](#8)
* [步骤 9: 安装OpenCV依赖软件包](#9-opencv)
* [步骤 10: 设置虚拟环境](#10)
* [步骤 11: 安装驴子车Python环境](#11-python)
* [步骤 12: 安装OpenCV组件](#12-opencv)
* 接下来 [创建你的驴子车应用](/guide/create_application/)

## 步骤 1: 安装系统

You need to flash a micro SD image with an operating system.

1. Download [Raspian Lite](https://downloads.raspberrypi.org/raspbian_lite_latest) (300MB).
2. Follow OS specific guides [here](https://www.raspberrypi.org/documentation/installation/installing-images/).
3. Leave micro SD card in your machine and edit/create some files as below:

## 步骤 2: 初始化设置-WiFi

We can create a special file which will be used to login to wifi on first boot. More reading [here](https://raspberrypi.stackexchange.com/questions/10251/prepare-sd-card-for-wifi-on-headless-pi), but we will walk you through it.

On Windows, with your memory card image burned and memory disc still inserted, you should see two drives, which are actually two partitions on the mem disc. One is labeled __boot__. On Mac and Linux, you should also have access to the __boot__ partition of the mem disc. This is formated with the common FAT type and is where we will edit some files to help it find and log-on to your wifi on it's first boot.

> Note: If __boot__ is not visible right away, try unplugging and re-insterting the memory card reader.

* Start a text editor: `gedit` on Linux. Notepad++ on Windows. TextEdit on a Mac.
* Paste and edit this contents to match your wifi:
```
country=US
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
    ssid="<your network name>"
    psk="<your password>"
}

```

Replace `<your network name>` with the ID of your network. Leave the quotes. I've seen problems when the network name contained an apostrophe, like "Joe's iPhone".
Replace `<your password>` with your password, leaving it surrounded by quotes.
If it bothers you to leave your password unencrypted, you may change the [contents later](https://unix.stackexchange.com/questions/278946/hiding-passwords-in-wpa-supplicant-conf-with-wpa-eap-and-mschap-v2) once you've gotten the pi to boot and log-in.

* Save this file to the root of __boot__ partition with the filename `wpa_supplicant.conf`. On first boot, this file will be moved to `/etc/wpa_supplicant/wpa_supplicant.conf` where it may be edited later. If you are using Notepad on Windows, make sure it doesn't have a .txt at the end.

## 步骤 3: 初始化设置-树莓派的主机名称
> Note: This 步骤 only possible on a linux host pc. Otherwise you can set it up later in Raspi-config树莓派系统设置 after logging in to your pi.

We can also setup the hostname so that your Pi easier to find once on the network. If yours is the only Pi on the network, then you can find it with

```
ping raspberrypi.local
```

once it's booted. If there are many other Pi's on the network, then this will have problems. If you are on a Linux machine, or are able to edit the UUID partition, then you can edit the `/etc/hostname` and `/etc/hosts` files now to make finding your pi on the network easier after boot. Edit those to replace `raspberrypi` with a name of your choosing. Use all lower case, no special characters, no hyphens, yes underscores `_`.

```
sudo vi /media/userID/UUID/etc/hostname
sudo vi /media/userID/UUID/etc/hosts
```

## 步骤 4: 开启SSH

Put a file named __ssh__ in the root of your __boot__ partition.


Now you're SD card is ready. Eject it from your computer, put it in the Pi
and plug in the Pi.


## 步骤 5: 与树莓派建立连接

If you followed the above instructions to add wifi access you're Pi should
now be connected to your wifi network. Now you need to find it's IP address
so you can connect to it via SSH.

The easiest way (on Ubuntu) is to use the `findcar` donkey command. You can try `ping raspberrypi.local`. If you've modified the hostname, then you should try: `ping <your hostname>.local`. This will fail on a windows machine. Windows users will need the full IP address (unless using cygwin).

If you are having troubles locating your Pi on the network, you will want to plug in an HDMI monitor and USB keyboard into the Pi. Boot it. Login with:

* Username: __pi__
* Password: __raspberry__

Then try the command:

```
ifconfig wlan0
```

If this has a valid IPv4 address, 4 groups of numbers separated by dots, then you can try that with your SSH command. If you don't see anything like that, then your wifi config might have a mistake. You can try to fix with

```
sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
```

If you don't have a HDMI monitor and keyboard, you can plug-in the Pi with a CAT5 cable to a router with DHCP. If that router is on the same network as your PC, you can try:

```
ping raspberrypi.local
```

Hopefully, one of those methods worked and you are now ready to SSH into your Pi. On Mac and Linux, you can open Terminal. On Windows you can install [Putty](http://www.putty.org/), [one of the alternatives](https://www.htpcbeginner.com/best-ssh-clients-windows-putty-alternatives/2/), or on Windows 10 you may have ssh via the command prompt.

If you have a command prompt, you can try:

```
ssh pi@raspberrypi.local
```

or

```
ssh pi@<your pi ip address>
```

or via Putty.

* Username: __pi__
* Password: __raspberry__
* Hostname:`<your pi IP address>`

## 步骤 6: 升级树莓派系统套件

```bash
sudo apt-get update
sudo apt-get upgrade
```

## 步骤 7: Raspi-config树莓派系统设置

```bash
sudo Raspi-config树莓派系统设置
```

* change default password for pi
* change hostname
* enable Interfacing Options | I2C
* enable Interfacing Options | Camera
* Advanced Options | Exapand Filesystem

Choose <Finish> and hit enter.

> Note: Reboot after changing these settings. Should happen if you say yes.

## 步骤 8: 安装依赖软件包

```bash
sudo apt-get install build-essential python3 python3-dev python3-virtualenv python3-numpy python3-picamera python3-pandas python3-rpi.gpio i2c-tools avahi-utils joystick libopenjp2-7-dev libtiff5-dev gfortran libatlas-base-dev libopenblas-dev libhdf5-serial-dev git
```

## 步骤 9: 安装OpenCV依赖软件包

If you are going for a minimal install, you can get by without these. But it can be handy to have OpenCV.

```bash
sudo apt-get install libilmbase-dev libopenexr-dev libgstreamer1.0-dev libjasper-dev libwebp-dev libatlas-base-dev libavcodec-dev libavformat-dev libswscale-dev libqtgui4 libqt4-test
```

##  步骤 10: 设置虚拟环境

```bash
python3 -m virtualenv -p python3 env --system-site-packages
echo "source env/bin/activate" >> ~/.bashrc
source ~/.bashrc
```
Modifying your .bashrc in this way will automatically enable this environment each time you login. To return to the system python you can type `deactivate`.

##  步骤 11: 安装驴子车Python环境

* Change to a dir you would like to use as the head of your projects.

```
mkdir projects
cd projects
```

* Get the latest donkeycar from Github.

```bash
git clone https://github.com/autorope/donkeycar
cd donkeycar
git checkout master
pip install -e .[pi]
pip install tensorflow==1.13.1
```

You can validate your tensorflow install with

```bash
python -c "import tensorflow"
```

Warnings like this are normal:
```
/home/pi/env/lib/python3.5/importlib/_bootstrap.py:222: RuntimeWarning: compiletime version 3.4 of module 'tensorflow.python.framework.fast_tensor_util' does not match runtime version 3.5
  return f(*args, **kwds)
/home/pi/env/lib/python3.5/importlib/_bootstrap.py:222: RuntimeWarning: builtins.type size changed, may indicate binary incompatibility. Expected 432, got 412
  return f(*args, **kwds)
```

##  步骤 12: 安装OpenCV组件

If you've opted to install the OpenCV dependencies earlier, you can install Python OpenCV bindings now with

```bash
pip install opencv-python
python -c "import cv2"
```

And if no errors, you have OpenCV installed!

----

### 接下来, [创建你的驴子车应用](/guide/create_application/).
