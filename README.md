# Encryption-in-MPLS-Networks
This is an ongoing research for my Dissertation involving implementation of Encryption in the MPLS networks

Configurations used:


The project aims to simulate a network consisting of 3 MPLS switches (OVS) communicating with eachother on a virtual network (mininet) with an added functionality of encryption in the MPLS payload as specified in https://tools.ietf.org/html/draft-ietf-mpls-opportunistic-encrypt-03

The project implementation consists of 4 parts:
1) Initial considerations:
	Ubuntu 16.04.3 LTS
	Kernel version 4.13.0-45-generic
	GCC compiler 4.6 or later

2) Installation of technologies:
	Run the "1-InstallationScript.sh" script in the scripts folder.

3) OpenVSwitch setup:
	The OpenVSwitch code needs to be compiled and its kernel modules needs to be created. 
	This module is then installed and loaded in the linux kernel.
	Navigate inside 'ovs' folder and run the "2-OVSSetup.sh" script.

4) Project execution:
	We start by first creating our virtual network and the OpenVSwitch switches in this network.
		Run the "3-NetworkSetupScript.sh" script in the scripts folder.
	Execute the command in a different terminal: $sudo mn --topo linear,3 --switch ovsk.
	Once the network has been setup we add the MPLS flows to the switches.
		Run the "4-AddFlowScript.sh" script in the scripts folder.
	In mininet terminal execute the following command: h1 ping h3

Monitoring: Currently monitoring all the packets using wireshark.

Reference:
http://tocai.dia.uniroma3.it/compunet-wiki/index.php/MPLS_with_OpenFlow:_howto#Setup_of_OpenFlow_rules_.28Open_vSwitch.29

https://github.com/mininet/openflow-tutorial/wiki/docs.openvswitch.org/en/latest/tutorials/

http://docs.openvswitch.org/en/latest/intro/install/general/


