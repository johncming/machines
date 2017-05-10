# 4 hosts
boxes = [
  {
    :name => "n0",
    :box => "ubuntu/xenial64",
    :cpu => "33",
    :ram => "1024"
  },
  {
    :name => "n1",
    :box => "ubuntu/xenial64",
    :cpu => "33",
    :ram => "1024"
  },
  {
    :name => "n2",
    :box => "ubuntu/xenial64",
    :cpu => "33",
    :ram => "1024"
  },
  {
    :name => "n3",
    :box => "ubuntu/xenial64",
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

      config.landrush.enabled = true

      # use domain(landrush) globally.
      vms.ssh.private_key_path = "./insecure_private_key"
      vms.ssh.insert_key = false

    end
  end
end
