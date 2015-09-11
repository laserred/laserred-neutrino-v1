# SET YOUR HOSTNAME ADDRESS HERE
#################################

host_name = [projectname].local

#################################

Vagrant.configure(2) do |config|

  config.vm.box_url = "http://laserred.co/vagrant/laserred.box"
  config.vm.box = "laserred.box"
  config.ssh.insert_key = false
  config.vm.network "public_network", ip: public_ip
  config.vm.hostname = host_name
  config.vm.post_up_message = "Laser Red Neutrino is now running on: #{host_name}"

  #run puppet to get the latest WP version and install it.
  config.vm.provision :puppet do |puppet|
    puppet.manifests_path = "puppet/manifests"
    puppet.module_path = "puppet/modules"
    puppet.manifest_file  = "init.pp"
  end

  # Fix for slow external network connections
  config.vm.provider :virtualbox do |vb|
    vb.memory = 1024 #1 gig of RAM, if you're having speed problems and have a decent amount of RAM 2048 is probably a better number
    vb.customize ['modifyvm', :id, '--natdnshostresolver1', 'on']
    vb.customize ['modifyvm', :id, '--natdnsproxy1', 'on']
  end

end