# octoprint_on_orangepi

## Commands

default user: root, password: 1234


----- Add user --------

Create new user (user:pi) 
su pi 
cd ~
sudo visudo
pi ALL=(ALL) NOPASSWD:ALL (put this on the last line of file)

----- Upgrade --------
sudo apt-get update
sudo apt-get upgrade

sudo usermod -a -G tty pi
sudo usermod -a -G dialout pi
sudo usermod -a -G video pi

----- Install dependencies --------

sudo apt install python3 python3-pip python3-dev python3-setuptools python3-venv git libyaml-dev build-essential libffi-dev libssl-dev
mkdir OctoPrint && cd OctoPrint
python3 -m venv venv
source venv/bin/activate
pip3 install --upgrade pip
pip3 install octoprint
exit

----- Test --------
~/OctoPrint/venv/bin/octoprint serve

----- Automatic startup -------
wget https://github.com/OctoPrint/OctoPrint/raw/master/scripts/octoprint.service && sudo mv octoprint.service /etc/systemd/system/octoprint.service
systemctl enable octoprint.service
sudo service octoprint start

----- OctoPrint server commands ------
restart octoprint - sudo service octoprint restart
restart system - sudo shutdown -r now
shutdown system - sudo shutdown -h now


