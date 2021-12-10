# SmartArmStack (Research Only packages)

This repository contains all Research Only packages related to the [SmartArm](http://doi.org/10.1002/rcs.2053) development.

The current version of the packages are compatible with `ROS Noetic` in `Ubuntu 20.04 Focal`.

## Installation and updates
The only supported strategy is to download the latest `.deb` files and install them in your system.

You can download them manually at the [Releases](https://github.com/SmartArmStack/smart_arm_stack_researchonly/releases) page.

To do it on the command line, you might do:

Install `curl` and `jq`.
```sh
sudo apt update && sudo apt install curl jq
```

Run the following to install or update.
```sh
# Make a temporary directory
mkdir -p ~/smart_arm_stack_researchonly_installation
cd ~/smart_arm_stack_researchonly_installation
# Remove existing packages, if any
sudo apt remove ros-noetic-sas* -y
# Download files
wget $(curl -sL https://api.github.com/repos/smartarmstack/smart_arm_stack_researchonly/releases/latest | jq -r '.assets[].browser_download_url')
# Install packages
sudo dpkg -i  ros-noetic-sas-*.deb
# Remove temporary folder
rm -r ~/smart_arm_stack_researchonly_installation
```

## Dependencies

1. [SmartArmStack LGPLv3 packages](https://github.com/SmartArmStack/smart_arm_stack) and its dependencies.

2. QtNetwork

```sh
sudo apt install libqt5network5
```

## Issues

If you have any trouble, open an [issue](https://github.com/SmartArmStack/smart_arm_stack_researchonly/issues).
