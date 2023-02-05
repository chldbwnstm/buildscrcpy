# buildscrcpy

1) VM a debian 11
2) Follow instructions
3) # Install latest JDK
sudo apt install default-jdk
export ANDROID_SDK_ROOT=/usr/lib/android-sdk

#download android sdk
Go to https://developer.android.com/studio/index.html Then down to Command line tools only Click on Linux link, accept the agreement and instead of downloading right click and copy link address

cd $ANDROID_SDK_ROOT
sudo wget https://dl.google.com/android/repository/commandlinetools-linux-6858069_latest.zip
sudo unzip commandlinetools-linux-6858069_latest.zip

#move folders
Rename the unpacked directory from cmdline-tools to tools, and place it under $ANDROID_SDK_ROOT/cmdline-tools, so now it should look like: $ANDROID_SDK_ROOT/cmdline-tools/tools. And inside it, you should have: NOTICE.txt bin lib source.properties.

#set path
PATH=$PATH:$ANDROID_SDK_ROOT/cmdline-tools/latest/bin:$ANDROID_SDK_ROOT/cmdline-tools/tools/bin

cd $ANDROID_SDK_ROOT/cmdline-tools/tools/bin

#accept licenses
yes | sudo sdkmanager --licenses

sudo chmod 777 /usr/lib/android-sdk

#create local.properties inside scrcpy folder

cd ~/scrcpy
echo "sdk.dir=/usr/lib/android-sdk" > local.properties

sudo install make
sudo install zip

run ./release.sh without root
