# gym-Atari-SpaceInvaders-V0

The instruction is only for Ubuntu.

### Neon
Install prerequisites:

```
sudo apt-get install libhdf5-dev libyaml-dev libopencv-dev pkg-config
sudo apt-get install python python-dev python-pip python-virtualenv
```

Check out and compile the code:

```
git clone https://github.com/NervanaSystems/neon.git
cd neon
make
```
Set Python PATH to `NEON_HOME`. `NEON_HOME` is the path where neon is installed,

`export PYTHONPATH = NEON_HOME`

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

cd /tmp
git clone https://github.com/opencv/opencv.git
cd opencv
mkdir build
cd build
cmake -D CMAKE_BUILD_TYPE=RELEASE\
-D CMAKE_INSTALL_PREFIX=/usr/local\
-D WITH_TBB=ON \ 
-D WITH_V4L=ON \
-D WITH_QT=ON \
-D WITH_OPENGL=ON ..

make -j $(nproc)
make install

/bin/bash -c 'echo "/usr/local/lib" > /etc/ld.so.conf.d/opencv.conf'
ldconfig

ln /dev/null /dev/raw1394

cd /
rm -rf /tmp/opencv
```

Then just check out the code:

```
git clone https://github.com/tambetm/simple_dqn
cd simple_dqn
```
### Optional

For plotting install `matplotlib`:

`pip install matplotlib`

For producing game videos install `avconv`:

`sudo apt-get install libav-tools`

### To save video files

Replace `simple_dqn/agent.py` in the current code with `agent.py` in the current repository.

## Running the code
### For training, testing and saving the results in a csv file 

`python main.py game SpaceInvaders-V0 --environment "gym" --backend 'cpu' --random_steps 500 --train_steps 1000 --test_steps 500 --csv_file 'SpaceInvaders-V0.csv' `


