# gym-Atari-SpaceInvaders-V0

The instruction is only for Ubuntu.

### Neon
Install prerequisites:

`sudo apt-get install libhdf5-dev libyaml-dev libopencv-dev pkg-config`
`sudo apt-get install python python-dev python-pip python-virtualenv`

Check out and compile the code:

`git clone https://github.com/NervanaSystems/neon.git`

`cd neon`

`make`

pip install gym

pip install gym[atari]

pip install numpy argparse logging

git clone https://github.com/tambetm/simple_dqn

cd simple_dqn

pip install matplotlib

sudo apt-get install libav-tools

To run training for Breakout:

./train.sh roms/breakout.bin
