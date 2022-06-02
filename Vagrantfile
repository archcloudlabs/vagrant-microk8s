# -*- mode: ruby -*-
Vagrant.configure("2") do |config|
  config.vm.box = "generic/ubuntu2004"
   config.vm.provider "libvirt" do |vb| # set provider to your hypervisor (virtualbox/libvirt/etc...)
     vb.memory = "2048"
   end

  config.vm.provision "shell", inline: <<-SHELL
	snap install microk8s --classic && \
    sudo usermod -a -G microk8s vagrant && \
    chown -f -R vagrant ~/.kube
   SHELL
end
