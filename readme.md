# Laser Red Neutrino
## A simple wordpress vagrant environment

### Installation
1. Clone this repo into your project folder.
2. Edit the Vagrantfile to add a static IP address.
3. `vagrant up`
4. Profit.

**If you have a local copy of laserred.box you can comment out the line of the Vagrantfile containing `config.vm.box_url = "http://laserred.co/vagrant/laserred.box"` (Add a `#` in front of it).** 

**If you don't do this, Vagrant will try to download the box which, is nearly 700mb.**