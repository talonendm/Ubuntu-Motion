# Ubuntu-Motion
Motion setup etc.





# some tests:

;area_detect value
 -->
area_detect value 4 5 6

# Noise threshold for the motion detection (default: 32)
noise_level 32
-->
# Noise threshold for the motion detection (default: 32)
noise_level 42





# set-up:


sudo apt-get install motion


Adding user motion  - 

Warning: The home dir /var/lib/motion you specified already exists.
Adding system user `motion' (UID 111) ...
Adding new user `motion' (UID 111) with group `motion' ...
The home directory `/var/lib/motion' already exists.  Not copying from `/etc/skel'.
adduser: Warning: The home directory `/var/lib/motion' does not belong to the user you are currently creating.
Adding user `motion' to group `video' ...
Adding user motion to group video
Done.
Setting up qt-faststart (7:2.5.8-0ubu



daemon is disabled 



cd /etc/motion
clear
ls

if single camera, no worry about thread files.. mulla nyt vaan yks camera, joten ei näy thread.conf tiedostoja

tai global configuration motion.conf, eli monta kameraa pitäis toimia kans tollee..


GEDIT

$ sudo add-apt-repository ppa:ricotz/staging

$ sudo add-apt-repository ppa:gnome3-team/gnome3

$ sudo add-apt-repository ppa:gnome3-team/gnome3-staging

$ sudo add-apt-repository ppa:ricotz/testing



sudo apt-get update (errori)

sudo apt-get install gedit

---


sudo gedit motion.conf

sudo service motion start

sudo gedit /etc/default/motion


sudo gedit ~/.motion/motion.conf


START:

sudo motion

http://localhost:8081/

sudo service motion stop


http://www.lavrsen.dk/foswiki/bin/view/Motion/FrequentlyAskedQuestions

A USB camera uses all the bandwidth a USB1.1 controller can give. Even at low framerates the camera reserves more than half the 11 Mb/s. This means that the 2nd camera gets rejected. Few motherboards have more than one controller. Often 2 or 4 physical connections on a motherboard shares one and the same USB controller. To add more cameras you need to put USB adapter cards. One per camera. There exists cards with full bandwidth per USB socket. These present themselves as for example 4 USB controllers to Linux and they work fine with 4 cameras. Also, many (if not most) cheap PCI USB1/2 cards ($10 range) have a controller capable of supporting 2 x USB1 cameras and an additional USB2 camera per card. With those cards and USB1 extender cards (allowing extension of a USB1 device for up to 100m, typically 50m) you can have a capable surveillance setup using only USB cameras.



target_dir /var/lib/motion
-->
target_dir /var/lib/motion
target_dir /home/jaakko/motionjt


picture_filename %v-%Y%m%d%H%M%S-%q

toi %v- pois.. 




dropbox
https://www.dropbox.com/install?os=lnx

Dropbox Headless Install via command line
The Dropbox daemon works fine on all 32-bit and 64-bit Linux servers. To install, run the following command in your Linux terminal.

32-bit:

cd ~ && wget -O - "https://www.dropbox.com/download?plat=lnx.x86" | tar xzf -


Next, run the Dropbox daemon from the newly created .dropbox-dist folder.

~/.dropbox-dist/dropboxd
If you're running Dropbox on your server for the first time, you'll be asked to copy and paste a link in a working browser to create a new account or add your server to an existing account. Once you do, your Dropbox folder will be created in your home directory. Download this Python script to control Dropbox from the command line. For easy access, put a symlink to the script anywhere in your PATH.




1606xx more some edits:

aakko-HP:~$ This package provides a command-line tool and a Nautilus extension that integrates the Dropbox web service with your GNOME Desktop. 

tar xjf ./nautilus-dropbox-1.6.1.tar.bz2

tar xjf ./nautilus-dropbox-1.6.1.tar.bz2

cd ./nautilus-dropbox-1.6.1; ./configure; make; make install;

sudo apt-get update && sudo apt-get install pkgconfig

151206

# Detect motion in predefined areas (1 - 9). Areas are numbered like that:  1 2 3
# A script (on_area_detected) is started immediately when motion is         4 5 6
# detected in one of the given areas, but only once during an event.        7 8 9
# One or more areas can be specified with this option. Take care: This option
# does NOT restrict detection to these areas! (Default: not defined)
area_detect value 9


näin oli: 
; area_detect value 



WIFI check:

jaakko@Jaakko-HP:~$ lspci -nn -d 14e4:
10:00.0 Ethernet controller [0200]: ...
30:00.0 Network controller [0280]: ....

sudo reboot
sudo apt-get install firmware-b43-installer


dia asennus

sudo apt-get install dia





R


http://cran.r-project.org/bin/linux/ubuntu/README
Once I did that, everything installed fine.
https://github.com/hadley/devtools/issues/847

in your /etc/apt/sources.list file, replacing <my.favorite.cran.mirror> by the actual URL of your favorite CRAN mirror. See https://cran.r-project.org/mirrors.html for the list of CRAN mirrors. To install the complete R system, use

    sudo apt-get update
    sudo apt-get install r-base

Users who need to compile R packages from source [e.g. package maintainers, or anyone installing packages with install.packages()] should also install the r-base-dev package:

    sudo apt-get install r-base-dev
