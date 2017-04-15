Vagrant.configure('2') do |config|
  config.vm.box      = 'ubuntu/xenial64'
  config.vm.hostname = 'mongo.loc'
  config.vm.network 'private_network', ip: '192.168.33.12'

  config.vm.provider :virtualbox do |vb|
    vb.name   = 'vMongoDB'
    vb.cpus   = 2
    vb.memory = 1024
    vb.customize ['modifyvm', :id, '--ioapic', 'on']
  end

  config.vm.provision 'ansible' do |ansible|
    ansible.playbook = 'provisioning/playbook.yml'
    ansible.verbose  = 'v'
  end
end
