Virtual private cloud (vpc):A secure ,individual,private cc model hosted within a public c
here:
on vpc customers can run code host websites store data n anything else that can be done on private c
a vitual private cloud is hosted remotely by a public cloud provider
this means vpc combine scabalility n conveninve of public cloud computing

vpc n/w conncet google cloud resources to each other n to internet
this includes segmenting n/w,using firewalls rules to restrict access to instaces,n creating static routes to forward traffic n google vpc n/w are gloabal n can have subnets in any google cloud region worldwide

the architexture makes it easy to define nw layouts with gloabal scope 
resources can even be in different nzones on same subnet 
the size of subnet can be increased by ecpanding eange of ip addresses allocated to it n doing so wont affect vm that are already configured 
eg lets take vpc nw named vpc 1 that has 2 subnets defined in asia east 1 n us east 1 n if vpc has three compute engine vms attached to it means theyre neighorbs on the same subnet even though they r in different zones this capability can be used to build solutions that are resilient to disruptions yet retain a simple n/w layout 