# octoprint_on_orangepi

## Commands

default user: root, password: 1234<br />
<br />

### ----- Add user --------<br />

Create new user (user:pi) <br />
su pi <br />
cd ~<br />
sudo visudo<br />
pi ALL=(ALL) NOPASSWD:ALL (put this on the last line of file)<br />

### ----- Upgrade --------
sudo apt-get update<br />
sudo apt-get upgrade<br />
<br />
sudo usermod -a -G tty pi<br />
sudo usermod -a -G dialout pi<br />
sudo usermod -a -G video pi<br />

### ----- Install dependencies --------

sudo apt install python3 python3-pip python3-dev python3-setuptools python3-venv git libyaml-dev build-essential libffi-dev libssl-dev<br />
mkdir OctoPrint && cd OctoPrint<br />
python3 -m venv venv<br />
source venv/bin/activate<br />
pip3 install --upgrade pip<br />
pip3 install octoprint<br />
exit<br />

### ----- Test --------
~/OctoPrint/venv/bin/octoprint serve<br />
<br />
### ----- Automatic startup -------
wget https://github.com/OctoPrint/OctoPrint/raw/master/scripts/octoprint.service && sudo mv octoprint.service /etc/systemd/system/octoprint.service<br />
systemctl enable octoprint.service<br />
sudo service octoprint start<br />

### ----- OctoPrint server commands ------
restart octoprint - sudo service octoprint restart<br />
restart system - sudo shutdown -r now<br />
shutdown system - sudo shutdown -h now<br />


