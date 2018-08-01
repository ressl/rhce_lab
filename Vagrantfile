# Install required Vagrant plugins
missing_plugins_installed = false
required_plugins = %w[vagrant-cachier vagrant-hostsupdater vagrant-scp]

required_plugins.each do |plugin|
  unless Vagrant.has_plugin? plugin
    system "vagrant plugin install #{plugin}"
    missing_plugins_installed = true
  end
end

# If any plugins were missing and have been installed, re-run vagrant
exec "vagrant #{ARGV.join(' ')}" if missing_plugins_installed

Vagrant.configure('2') do |config|
  config.vm.define :server1 do |server1|
    server1.vm.box = 'bento/centos-7.5'
    server1.vm.hostname = 'server1.example.com'
    server1.vm.network :private_network, ip: '192.168.122.150', netmask: '255.255.225.0'
    server1.vm.provider 'virtualbox' do |vb|
      vb.cpus = '2'
      vb.memory = '1024'
      vb.name = 'rhce_lab_server1'
      vb.customize ['modifyvm', :id, '--vram', '8']
      vb.customize ['modifyvm', :id, '--audio', 'none']
      # vb.audio = 'none'
    end
  end
  config.vm.define :tester1 do |tester1|
    tester1.vm.box = 'bento/centos-7.5'
    tester1.vm.hostname = 'tester1.example.com'
    tester1.vm.network :private_network, ip: '192.168.100.100', netmask: '255.255.225.0'
    tester1.vm.provider 'virtualbox' do |vb|
      vb.cpus = '2'
      vb.memory = '1024'
      vb.name = 'rhce_lab_tester1'
      vb.customize ['modifyvm', :id, '--vram', '8']
      vb.customize ['modifyvm', :id, '--audio', 'none']
    end
  end
  config.vm.define :outsider1 do |outsider1|
    outsider1.vm.box = 'bento/centos-7.5'
    outsider1.vm.hostname = 'outsider1.example.org'
    outsider1.vm.network :private_network, ip: '192.168.122.50', netmask: '255.255.225.0'
    outsider1.vm.provider 'virtualbox' do |vb|
      vb.cpus = '2'
      vb.memory = '1024'
      vb.name = 'rhce_lab_outsider1'
      vb.customize ['modifyvm', :id, '--vram', '8']
      vb.customize ['modifyvm', :id, '--audio', 'none']
    end
  end
end
