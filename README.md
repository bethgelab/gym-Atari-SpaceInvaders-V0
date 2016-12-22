# gym-Atari-SpaceInvaders-V0

The instruction is only for Ubuntu.

### Neon
Install prerequisites:

```
sudo apt-get install libhdf5-dev libyaml-dev libopencv-dev pkg-config`
sudo apt-get install python python-dev python-pip python-virtualenv
```

Check out and compile the code:

```
git clone https://github.com/NervanaSystems/neon.git
cd neon
make
```

### OpenAI Gym

Install OpenAI Gym:

```
pip install gym
pip install gym[atari]
```

### Simple DQN

Prerequisities:

`pip install numpy argparse logging`

To install openCV

```
sudo apt-get install python-opencv
ln -s /usr/lib/python2.7/dist-packages/cv2.so NEON_HOME/.venv/lib/python2.7/site-packages/
In case it doen't work try following,

echo "deb http://archive.ubuntu.com/ubuntu/ trusty main restricted universe multiverse" >> /etc/apt/sources.list
apt-get update

apt-get -y install libopencv-dev build-essential cmake git libgtk2.0-dev pkg-config python-dev python-numpy libdc1394-22 libdc1394-22-dev libjpeg-dev libpng12-dev libtiff4-dev libjasper-dev libavcodec-dev libavformat-dev libswscale-dev libxine-dev libgstreamer0.10-dev libgstreamer-plugins-base0.10-dev libv4l-dev libtbb-dev libqt4-dev libfaac-dev libmp3lame-dev libopencore-amrnb-dev libopencore-amrwb-dev libtheora-dev libvorbis-dev libxvidcore-dev x264 v4l-utils unzip
```

cd /tmp
git clone https://github.com/opencv/opencv.git
cd opencv
mkdir build
cd build
cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr/local -D WITH_TBB=ON -D WITH_V4L=ON -D WITH_QT=ON -D WITH_OPENGL=ON ..
make -j $(nproc)
make install

git clone https://github.com/tambetm/simple_dqn

cd simple_dqn

pip install matplotlib

sudo apt-get install libav-tools

To run training for Breakout:

./train.sh roms/breakout.bin
