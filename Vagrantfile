

# SET YOUR IP ADDRESS HERE
#################################

public_ip = "YOUR IP"

#################################

Vagrant.configure(2) do |config|
  
  config.vm.box_url = "http://laserred.co/vagrant/laserred.box"
  config.vm.box = "laserred.box"
  config.vm.network "public_network", ip: public_ip
  config.vm.hostname = (0...10).map { ('a'..'z').to_a[rand(26)] }.join + ".neutrino.dev"
  config.vm.post_up_message = "Laser Red Neutrino is now running on ip address: #{public_ip}"

  #run puppet to get the latest WP version and install it.
  config.vm.provision :puppet do |puppet|
    puppet.manifests_path = "puppet/manifests"
    puppet.module_path = "puppet/modules"
    puppet.manifest_file  = "init.pp"
    #puppet.options="--verbose --debug"
  end

  # Fix for slow external network connections
  config.vm.provider :virtualbox do |vb|
    vb.memory = 1024
    vb.customize ['modifyvm', :id, '--natdnshostresolver1', 'on']
    vb.customize ['modifyvm', :id, '--natdnsproxy1', 'on']
  end

end
