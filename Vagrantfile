# SET YOUR HOSTNAME ADDRESS HERE
#################################

host_name = "test"

#################################

Vagrant.configure(2) do |config|

  config.vm.box_url = "http://laserred.co/vagrant/neutrino-v2.box"
  config.vm.box = "neutrino-v2.box"
  config.vm.hostname = "#{host_name}"
  config.vm.network "public_network"
  config.vm.post_up_message = "*******************************************\n\nIf this is the first boot of this box,\nyou will need to reboot it \nbefore you can access it by hostname\n\n*******************************************\n\nLaser Red Neutrino is now running on: #{host_name}.local"
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
