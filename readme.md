# Laser Red Neutrino
## A simple wordpress vagrant environment

### Installation
1. Clone this repo into your project folder.
2. Edit the Vagrantfile to add a static IP address.
3. `vagrant up`
4. Profit.

**If you have a local copy of laserred.box you can comment out the line in the Vagrantfile containing:**

**`config.vm.box_url = "http://laserred.co/vagrant/laserred.box"` (Add a `#` in front of it).**

**If you don't do this, Vagrant will try to download the box, which is nearly 700mb.**

### Help
If you get a recurring **Authentication failure. Retrying** error try the following.

1. CTRL-C to cancel the connection.
2. `ssh vagrant@localhost -p 2222`
3. `echo "ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEA6NF8iallvQVp22WDkTkyrtvp9eWW6A8YVr+kz4TjGYe7gHzIw+niNltGEFHzD8+v1I2YJ6oXevct1YeS0o9HZyN1Q9qgCgzUFtdOKLv6IedplqoPkcmF0aYet2PkEDo3MlTBckFXPITAMzF8dJSIFo9D8HfdOV0IAdx4O7PtixWKn5y2hMNG0zQPyUecp4pzC6kivAIhyfHilFR61RGL+GPXQ2MWZWFYbAGjyiYJnAmCP3NOTd0jMZEnDkbUvxhMmBYSdETk1rRgm+R4LOzFUGaHqHDLKLX+FIPKcF96hrucXzcWyLbIbEgE98OHlnVYCzRdK8jlqm8tehUc9c9WhQ== vagrant insecure public key" > .ssh/authorized_keys`

This will insert the Vagrant public key into authorized_keys and allow you to connect.
