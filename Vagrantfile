Vagrant.configure(2) do |config|
  
  config.vm.box_url = "http://laserred.co/vagrant/laserred.box"
  config.vm.box = "laserred.box"
  config.vm.network "public_network", ip: "ADD YOUR IP HERE"
  config.vm.hostname = (0...10).map { ('a'..'z').to_a[rand(26)] }.join
  config.vm.post_up_message = "Laser Red - vagrant box up"

  #run puppet to get the latest WP version and install it.
  config.vm.provision :puppet do |puppet|
    puppet.manifests_path = "puppet/manifests"
    puppet.module_path = "puppet/modules"
    puppet.manifest_file  = "init.pp"
    #puppet.options="--verbose --debug"
  end

  # Fix for slow external network connections
  config.vm.provider :virtualbox do |vb|
    vb.memory = 2048
    vb.customize ['modifyvm', :id, '--natdnshostresolver1', 'on']
    vb.customize ['modifyvm', :id, '--natdnsproxy1', 'on']
  end

end
