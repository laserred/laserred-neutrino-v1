# Laser Red Neutrino
## A simple wordpress vagrant environment

### Installation
1. Clone this repo into your project folder.
2. Edit the Vagrantfile to add a hostname.
3. `vagrant up`
4. On first boot, you will need to run `vagrant reload` in order for the hostname to be recognised on the network.

**If you have a local copy of laserred.box you can comment out the line in the Vagrantfile containing:**

**`config.vm.box_url = "http://laserred.co/vagrant/neutrino-v2.box"` (Add a `#` in front of it).**

**If you don't do this, Vagrant will try to download the box, which is nearly 700mb.**

**If you're experiencing 'Authentication failed' errors, see the wiki**
