These are the files to setup an hadoop cluster through virtual machines (VM) in one computer for testing. The goal is to have a minimalist but realistic cluster for testing, something closer to real word cluster than a pseudo cluster with all services running in 1 VM. It is based on Ubuntu 12.04 (Precise Pangolin)-64 Bits.

The computer must have enough RAM to run 4 virtual machines in parallel, at least 10 GB. It runs successfully on a 2012 MacBook pro with 16GB of RAM.

The setup is based on virtualbox as virtualization engine. It makes use of vagrant, a tool to help setup virtualbox VMs (guest-addition, port-forwarding, shared folder) and use them (power up and down). Both tools need to be installed. The VMs will run in "headless" mode (i.e. no GUI). Need to connect to them from ssh. An Ubuntu 12.04 box need to be available through Vagrant (called 'Precise64' in my case).

To use (some steps may be off/inaccurate/missing since it was setup some time ago, if so, please notify):
 * Create a folder, put the 'Vagrantfile' file in it, type 'Vagrant up' from that folder in a terminal on your host OS. This will create and setup all 4 VMs. All 4 VMs will have your current folder as the shared folder, so the content in that folder on your host OS is available to every VMs. All VMs will be part of a network internal to the computer, so no interaction with the home/office wifi/lan network.
 * Follow instructions in clusterCDH_setup.txt to configure the network details on each machine, to install cloudera manager (CM) on node1 and then to leave CM install hadoop on all nodes. This is not fully automated for now. Could do that later through chef or puppet which can be called by vagrant.
