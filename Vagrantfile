boxes = [
  {
    :name => "node-0",
    :box => "ubuntu/xenial64",
    :ip => '192.168.67.10',
    :cpu => "33",
    :ram => "1024"
  },
  {
    :name => "node-1",
    :box => "ubuntu/xenial64",
    :ip => '192.168.67.11',
    :cpu => "33",
    :ram => "1024"
  },
  {
    :name => "node-2",
    :box => "ubuntu/xenial64",
    :ip => '192.168.67.12',
    :cpu => "33",
    :ram => "1024"
  },
  {
    :name => "node-3",
    :box => "ubuntu/xenial64",
    :ip => '192.168.67.13',
    :cpu => "33",
    :ram => "1024"
  },
]

Vagrant.configure("2") do |config|
  boxes.each do |box|
    config.vm.define box[:name] do |vms|
      vms.vm.box = box[:box]

      vms.vm.provider "virtualbox" do |v|
        v.customize ["modifyvm", :id, "--cpuexecutioncap", box[:cpu]]
        v.customize ["modifyvm", :id, "--memory", box[:ram]]
      end

      vms.vm.network :private_network, ip: box[:ip]

      config.ssh.private_key_path = "./private_key"
    end
  end
end
