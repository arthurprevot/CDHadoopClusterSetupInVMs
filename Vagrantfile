
Vagrant::Config.run do |config|
  config.vm.define :node1 do |node1_config| ### cloudera manager server, NameNode, JobTracker, NameNode2, DataNode and TaskTracker # note: as suggested by cloudera manager during install.
    node1_config.vm.box = "precise64"
    #node1_config.vm.forward_port 7180, 7180 # cloudera manager
    node1_config.vm.network :hostonly, "222.222.222.201"
    node1_config.vm.host_name = "node1"
    #node1_config.vm.customize do |vm|
    #  vm.memory_size = 3029
    #end
    node1_config.vm.customize ["modifyvm", :id, "--memory", 3029] # i.e. allocate 3GB of RAM
  end

  config.vm.define :node2 do |node2_config| ### DataNode and TaskTracker
    node2_config.vm.box = "precise64"
    #node2_config.vm.forward_port 3306, 3306
    node2_config.vm.network :hostonly, "222.222.222.202"
    node2_config.vm.host_name = "node2"
    #node2_config.vm.customize do |vm|
    #  vm.memory_size = 3029
    #end
    node2_config.vm.customize ["modifyvm", :id, "--memory", 3029] # i.e. allocate 3GB of RAM
  end

  config.vm.define :node3 do |node3_config| ### DataNode and TaskTracker
    node3_config.vm.box = "precise64"
    #node3_config.vm.forward_port 3306, 3306
    node3_config.vm.network :hostonly, "222.222.222.203"
    node3_config.vm.host_name = "node3"
    #node3_config.vm.customize do |vm|
    #  vm.memory_size = 1546
    #end
    node3_config.vm.customize ["modifyvm", :id, "--memory", 1546] # i.e. allocate 1.5GB of RAM
  end

  config.vm.define :node4 do |node4_config| ### DataNode and TaskTracker
    node4_config.vm.box = "precise64"
    #node4_config.vm.forward_port 3306, 3306
    node4_config.vm.network :hostonly, "222.222.222.204"
    node4_config.vm.host_name = "node4"
    #node4_config.vm.customize do |vm|
    #  vm.memory_size = 1546
    #end
    node4_config.vm.customize ["modifyvm", :id, "--memory", 1546] # i.e. allocate 1.5GB of RAM
  end
end

## Setup for one machine, kept to see important ports. 
#Vagrant::Config.run do |config|
#  config.vm.box = "precise64"
#
#  #config.vm.forward_port 80, 1083
#  config.vm.forward_port 7180, 7180 # cloudera manager
#  config.vm.forward_port 50075, 50075 # datanode 
#  config.vm.forward_port 50070, 50070 # namenode
#  config.vm.forward_port 50030, 50030 # jobtracker 
#  config.vm.forward_port 8888, 8888 # Hue 
#
#  # No need to add shared folder, already enabled by default.
#end
#
## Need to run commands from pseudoCDH_setup.txt to add to setup.
