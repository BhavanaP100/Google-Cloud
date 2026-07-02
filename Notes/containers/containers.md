Containers is to give independent workload scalablity in paas 
Os and h/w abstraction layer in iaas
configurable system: customizable installation (favt runtime, webserver,db or middleware), configuration and buliding large slow and costly 
the smallest unit of compute is an app with its VM 
the guest os might be large even gigabytes in size n take min to boot 
as demand increases there is need of copying entire VM and boot the guest os for each instance of ur app which can be slow n costly 

A container is invisible box around your code and its dependiecies 
has limited access to its own partition of the file system n h/w
it only requires a few sys calls to create n start as quickly as a process
os needs an os kernel that supports containers and container runtime on each host 
scales like Paas but gives nealry the same flexibilty as iaas 

ex: lets say u want to scale a web server 
with a container u can do this in seconds and deploy dozens or hundreds of them depending on the size of ur workload on a single host 

suppose u want to build ur applications using lots of containers each  performing their own function like microservices if you build them this way and connect them with n/w connection , u can make them modular, deploy easily and scale independently across a group of hosts
the host can scale up and down and start and stop containers as demand for ur app changes or  as hosts fail