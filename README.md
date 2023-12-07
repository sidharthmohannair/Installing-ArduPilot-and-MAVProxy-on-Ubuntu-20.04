# Installing-ArduPilot-and-MAVProxy-on-Ubuntu-20.04
Below is a detailed guide for installing ArduPilot and MAVProxy on Ubuntu 20.04. Please note that this guide assumes a clean Ubuntu 20.04 installation.

## Install ArduPilot:
### 1. Update and Upgrade:
Open a terminal and run the following commands:
```bash
sudo apt update
sudo apt upgrade -y
```

### 2. Clone ArduPilot Repository:
Clone the ArduPilot repository:

```bash
cd ~
sudo apt install git
git clone https://github.com/ArduPilot/ardupilot.git
cd ardupilot
git checkout Copter-3.6
git submodule update --init --recursive
```
### 3. Install Dependencies:
Install dependencies needed for ArduPilot:

```bash
sudo apt install -y git python3-dev python3-opencv python3-wxgtk4.0 libxml2-dev
```
### 4. Build ArduPilot (Optional):
Build ArduPilot using the following commands:

Note: 

* You have already build Copter-3.6.

* To configure for a specific flight controller, use the following command:

```bash
cd ardupilot
./waf configure --board [Board_Type]

```
Replace [Board_Type] with the appropriate board type. For example:

* For CubeBlack:

```bash
cd ardupilot
./waf configure --board CubeBlack
```
* For CubeOrange:

```bash
cd ardupilot
./waf configure --board CubeOrange
```
After configuring, build ArduPilot:
```bash
./waf copter
```

To view the available board options for configuring ArduPilot, you can use the following command:

```bash
./waf list_boards
```

## Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

Please make sure to update tests as appropriate.
