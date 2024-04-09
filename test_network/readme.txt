
---- Simple Deep Packet inspection topology with sdn --
SDN network will be created with mininet 
two hosts will be attached to  switch and switch will be controlled by openflow controller. 
one host will use scapy to generate test packest and send to the switch 
other host will listen the network.

when first host send packet to the switch , switch send this packet to the controller 
controller will check this packet with ai. if  packet approved it will send to the other port 
otherwise it will drop 
