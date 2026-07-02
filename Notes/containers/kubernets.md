kubernetes open souce platform for managing containrized workloads and services 
makes it easy to orchestrate many containers on many hosts scale them as microservices and deploy rollouts n rollbacks
Is a set of APIs to deploy containers on set of nodes called a cluster 
system id divided into a set of primary components that run as the control plane and a set of nodes that run containers 
in kubernetes a node represents a computing instances like a machine 
you descirbe a set of applications and how they should interact with each other  and kubernetes figures how to make it happen 

a pod is smallest unit in kubernetes that u create or deploy 
it reperesnts  app component and entire app

generally u have only one container per pod but if you have multiple containers with a hard dependency you can package them onto a single pod and share n/w and shtorage resources between them 

the pod provides a unique n/w ip n set of ports for your containers and configurable option that govern how your containers should run 
one way to run a container in pod in kuberntes is to use the kubectl run command which starts deployment with container running inside a pod 

a deployment represents a group of replicas of the same pod and keeps your pods running even when the nodes they run on fail

a deployment could represent a component of an application or even an entire app 
to see a list of running pods in ur project run a commans: $kubectl get pods

kubernetes creates a servce with a fixed Ip address for your pods and a controller says i need to attach an external load balancer with a public ip address to that service so others outside cluster can access it 

in GKE the load balancer is created as a n/w load balancer 
any client that reaches that IP address will be routes to POd behind the service a service is an abstraction which defines a logical set of pods and policy by which to access them 
as deployment create and destroy pods pods will be assigned their own IP addresses but those addresses dont remain stable over time

A serive grp is a set of pods and provides a stable endpoint for them 
eg if u create frontend n backend n put them behind their own services the backend pods might change but frontend pods are not aware of this 
they simply refer to backend service 
to scale a deployment run kubectl scale command
eg:........

instead of issuing commands u can provide a configuration file that tells kubernetes what you want your desrired state to look like and kubernetes determine how to do it 
you accomplish this by using a deployment config file 
you can check your deployment to make sure the proper no. of replicas is running by using either kubectl get deployments or kubetcl describe deployments
to run 5 replicas instead of three all you do is update the deployment config file and kubetcl apply command to use the update config file you can still reach your endpoint as before by using kubectl get services to get the external 

kubetcl rollout or change your deployment config file and then apply change using kubetcl apply 
new pods will be created acc to your new update strategy 
