# -*- mode: ruby -*-
# vi: set ft=ruby :

# Testing an ArduPilot VM:
# sim_vehicle.py # in the starting directory should start a Copter simulation
# xterm # X11 forwarding should work
# sim_vehicle.py --debug --gdb
# sim_vehicle.py --valgrind
# time (cd /vagrant && ./waf configure --board=fmuv2 && ./waf build --target=bin/ardusub) # ~9 minutes
# time (cd /vagrant && ./waf configure --board=fmuv3 && ./waf build --target=bin/ardusub) # ~ minutes (after building fmuv2)
# time (cd /vagrant && ./waf configure --board=navio2 && ./waf build --target=bin/arduplane)
# time (cd /vagrant && ./Tools/autotest/sim_vehicle.py --map --console -v ArduPlane -f jsbsim # should test JSBSim)
# time (cd /vagrant && ./Tools/autotest/autotest.py build.APMrover2 drive.APMrover2)

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
config.vm.synced_folder "./", "/vagrant"
  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #

  # If you are on windows then you must use a version of git >= 1.8.x
  # to update the submodules in order to build. Older versions of git
  # use absolute paths for submodules which confuses things.

  # removing this line causes "A box must be specified." error
  # and this is the default box that will be booted if no name is specified
  config.vm.box = "generic/ubuntu1804"

  # LTS, EOL April, 2019:
  config.vm.define "trusty32", autostart: false do |trusty32|
    config.vm.box = "ubuntu/trusty32"
    config.vm.provision "trusty32", type: "shell", path: "Tools/vagrant/initvagrant.sh"
    config.vm.provider "virtualbox" do |vb|
      vb.name = "ArduPilot (trusty32)"
      vb.gui = true
    end
  end

  # 14.04.5 LTS, EOL April, 2019:
  config.vm.define "trusty64", autostart: false do |trusty64|
    config.vm.box = "ubuntu/trusty64"
    config.vm.provision "trusty64", type: "shell", path: "Tools/vagrant/initvagrant.sh"
    config.vm.provider "virtualbox" do |vb|
      vb.name = "ArduPilot (trusty64)"
      vb.gui = true
    end
  end

  # LTS, EOL April 2021
  # this VM is useful for running valgrind on!
  config.vm.define "xenial32", autostart: false do |xenial32|
    config.vm.box = "ubuntu/xenial32"
    config.vm.provision :shell, path: "Tools/vagrant/initvagrant.sh"
    config.vm.provider "virtualbox" do |vb|
      vb.name = "ArduPilot (xenial32)"
      vb.gui = true
    end
  end

  # NO LONGER AVAILABLE FOR DOWNLOAD, EOL January 2018
  # EOL January 2018
  # Only kept around for those few dev's who have already got this image and continue to use it.
  config.vm.define "zesty32", autostart: false do |zesty32|
    config.vm.box = "ubuntu/zesty32"
    config.vm.provision :shell, path: "Tools/vagrant/initvagrant.sh"
    config.vm.provider "virtualbox" do |vb|
      vb.name = "ArduPilot (zesty32)"
      vb.gui = true
    end
  end

  # 17.10, EOL July 2018
  # Only kept around for those few dev's who have already got this image and continue to use it; not available for download
  config.vm.define "artful32", autostart: false do |artful32|
    config.vm.box = "ubuntu/artful32"
    config.vm.provision :shell, path: "Tools/vagrant/initvagrant.sh"
    config.vm.provider "virtualbox" do |vb|
      vb.name = "ArduPilot (artful32)"
      vb.gui = true
    end
  end

  # 18.04 LTS , bleeding edge.
  config.vm.define "bionic32", autostart: false do |bionic32|
    config.vm.box = "ubuntu/bionic32"
    config.vm.provision :shell, path: "Tools/vagrant/initvagrant.sh"
    config.vm.provider "virtualbox" do |vb|
      vb.name = "ArduPilot (bionic32)"
      vb.gui = true
    end
  end

  # 18.04 LTS , bleeding edge.
  config.vm.define "bionic64", primary: true do |bionic64|
    config.vm.box = "ubuntu/bionic64"
    config.vm.provision :shell, path: "Tools/vagrant/initvagrant.sh"
    config.vm.provider "virtualbox" do |vb|
      vb.name = "ArduPilot (bionic64)"
      vb.gui = true
    end
  end


  # 18.10 bleeding edge
  config.vm.define "cosmic32", autostart: false do |cosmic32|
    config.vm.box = "ubuntu/cosmic32"
    config.vm.provision :shell, path: "Tools/vagrant/initvagrant.sh"
    config.vm.provider "virtualbox" do |vb|
      vb.name = "ArduPilot (cosmic32)"
      vb.gui = true
    end
  end

  # 18.10 bleeding edge
  config.vm.define "cosmic64", autostart: false do |cosmic64|
    config.vm.box = "ubuntu/cosmic64"
    config.vm.provision :shell, path: "Tools/vagrant/initvagrant.sh"
    config.vm.provider "virtualbox" do |vb|
      vb.name = "ArduPilot (cosmic64)"
      vb.gui = true
    end
  end

  # 18.10 bleeding edge
  config.vm.define "ubuntu1804-hyperv", autostart: false do |cosmic64|
    config.vm.box = "generic/ubuntu1804"
    config.vm.provision :shell, path: "Tools/vagrant/initvagrant.sh"
  end

end
