#this compile environment is for FaeaF2S
#May also work for other MTK6589 devices.
#http://www.faeamobile.com/
#System Requirement:
#ubuntu-12.04.3-server-amd64
#Hardware Requirement:
#memory >=4GB, disk free space >50GB


sudo su

apt-get update

apt-get install unzip

unzip ./adt-bundle-linux-x86-20130729.zip -d /opt/

mv /opt/adt-bundle-linux-x86-20130729/ /opt/adt-bundle-linux-x86/

tar zxvf ./arm-eabi-4.4.3.tar.gz -C /opt/

tar xvf ./wine-1.3.22.tar.bz2  -C /opt/

tar xvf ./android-sdk_r22.3-linux.tar   -C /opt/

mv /opt/android-sdk-linux/ /opt/android-sdk-linux-x86/

chmod 755 ./jdk-6u26-linux-x64.bin

cp ./jdk-6u26-linux-x64.bin /opt/

cd /opt/

./jdk-6u26-linux-x64.bin

apt-get install git-core gnupg flex bison gperf build-essential zip curl zlib1g-dev libc6-dev libc6-dev-i386 lib32ncurses5-dev ia32-libs x11proto-core-dev libx11-dev lib32readline-dev lib32z-dev lib32z1-dev libgl1-mesa-dev g++-multilib g++-4.4-multilib mingw32 tofrodos python-markdown libxml2-utils

mv /usr/bin/gcc /usr/bin/gcc.bak

ln -s /usr/bin/gcc-4.4 /usr/bin/gcc

mv /usr/bin/g++ /usr/bin/g++.bak

ln -s /usr/bin/g++-4.4 /usr/bin/g++


#Compile the source code for Faea F2s

source ./jdk6env.sh

./release-ota.sh e960 w d faea f2v3_mmd1_128g8g
