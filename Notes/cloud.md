cloud computig:**allows renting infrastructure ,runtime envi and service on pay peer user basis .cloud computig is way of using IT .
**Characteristics:**
1.customer get computing resource that are on demand and self service .
2.customers get acess to those resource over internet from anywhere .
3.The provider of those resource allocates them to user out of that pool.
4.Resources are elastic -means flexible so customer can be .
5.Customers pay only for what they use.

/fundamentals/

1.Iaas: Provides Raw compute,Storage and network capabilities,Here customers pay for what they allocate
eg:compute Engine 

2.Paas: Bind code to libraries that provide access to the infrastucture needs,This allows more resources to be focused on application logic
      in paas model customers pay for the resources they actually use  
eg:App Engine 

3.Saas:It provides entire application stack delivering an entire cloud based application that customers can access and use 
     these arent instaled locally on computer instead they run on cloud as serives and are  consumed directly over 
     the internet by end users  
eg:gmaol,drive etc 

/network/

Google cloud network : It is designed to give customers 
1.highest possible throughput 
2.lowest possible latencies
3.100+ content catching nodes world wide
4.High demand content is cached for quicker access


infrastructure is based on 7 major geographic locations:
1.North America
2.South America
3.Africa 
4.Middle east
5.Europe
6.Asia 
7.Austrilia

App loaction should be depend on availability ,durability and latency.
Latency: Measures the time a packet of information takes to travel from its source to its destination.

Each of these locations is divided into several different regions and zone
Regions:These represent independent geographic areas and are composed of zones.
eg: London/europe-west2 is region that has 3 zones 1.europe-west2-a,2.europe-west2-b,3.europe-west2-c.
Zone:A zone is area where Google Cloud resources are deployed.
eg:if you launch a vm using compute engine it will run in zones that you specify to ensure resource redundancy.

1.you can also run resources in different regions this is useful for bringing app closer to users around the world,and also for protection in case there are issues with an entire region like natural disaster.
2.Some of Gc services support placing resources in multi region
eg: spanner multi-region conf allow u to replicate the db data in multiple zones across multiple regions

Gc is providing 127 zones and 42 regions

/security/

Google infrastucture Security:

Hardware infrastructure layer 
1.hardware design and provenance 
2.Secure boot stack
3.Premises security 

Serive deployment layer
1.Encryption of inter-service communication

User identity layer
user identity

Storage services layer
1.Encyption at rest
2.Dos protection

operational security layer
1.Intrusion detection
2.Reducing insider risk
3.Employee universal second factor(U2f) use
4.software development practices


