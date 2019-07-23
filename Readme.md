## Get Started with the gstreamer-1.10 on Ubuntu14.04
In this wiki, we'll walk through the steps to set up the gstreamer-1.10 and get sample to test. Before you get started, we recommend watching Getting Started from [install](https://gstreamer.freedesktop.org/documentation/installing/index.html?gi-language=c).

### 2.5: Build gstreamer libraries
The sample app requires a media player implementation to play MP3 files; our implementation supports GStreamer. Before building GStreamer, you need to install some utilities and dependencies.

Run this command:

sudo apt-get install bison flex libglib2.0-dev libasound2-dev pulseaudio libpulse-dev

The following are also required to playback audio from iHeartRadio:

sudo apt-get install libfaad-dev libsoup2.4-dev libgcrypt20-dev

#### 2.5.1: Build gstreamer-1.10.4
First, we build source directroy - `SOURCE_FOLDER`
```sh
cd $SOURCE_FOLDER
wget https://gstreamer.freedesktop.org/src/gst-plugins-base/gst-plugins-base-1.10.4.tar.xz
tar xf gst-plugins-base-1.10.4.tar.xz
cd *gst-plugins-base*/
./configure --prefix=$LOCAL_BUILD
make -j3
sudo make install
```

#### 2.5.2: Build gst-plugins-base-1.10.4
```sh
cd $SOURCE_FOLDER
wget https://gstreamer.freedesktop.org/src/gst-plugins-base/gst-plugins-base-1.10.4.tar.xz
tar xf gst-plugins-base-1.10.4.tar.xz
cd *gst-plugins-base*/
./configure --prefix=$LOCAL_BUILD
make -j3
sudo make install
```
#### 2.5.3: Build gst-libav-1.10.4
```sh
cd $SOURCE_FOLDER
wget https://gstreamer.freedesktop.org/src/gst-libav/gst-libav-1.10.4.tar.xz
tar xf gst-libav-1.10.4.tar.xz
cd *gst-libav*/
./configure --prefix=$LOCAL_BUILD
make -j3
sudo make install
```
#### 2.5.4: Build gst-plugins-good-1.10.4
```sh
cd $SOURCE_FOLDER
wget https://gstreamer.freedesktop.org/src/gst-plugins-good/gst-plugins-good-1.10.4.tar.xz
tar xf gst-plugins-good-1.10.4.tar.xz
cd *gst-plugins-good*/
./configure --prefix=$LOCAL_BUILD
make -j3
sudo make install
```

#### 2.5.5: Build gst-plugins-bad-1.10.4 (Needed for iHeartRadio)
```sh
cd $SOURCE_FOLDER
wget https://gstreamer.freedesktop.org/src/gst-plugins-bad/gst-plugins-bad-1.10.4.tar.xz
tar xf gst-plugins-bad-1.10.4.tar.xz
cd *gst-plugins-bad*/
./configure --prefix=$LOCAL_BUILD
make -j3
sudo make install
```

