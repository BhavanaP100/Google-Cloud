cloud run is managed compute platform that run stateless containers via web requests or Pub/sub events 
it is serverless,removing the need for insfrastructure management that means it removes all infrastructure management tasks so you can focus on devloping applications 
its built on knative,an open API and runtime environment built on kubernetes 
it can be fully managed on google cloud on google kubernetes engine or anywhere knative 
can automatically scale up n down from 0 to almost instatenously charging only for the resources used 

3step process 
1.source code (using comfartable language build ur application )
2.build and package your application into a container image 
3.deploy to cloud run the container image is pushed to artifact resgistry where cloud run will deploy it 
once deployed container image will get a unique https url back
cloud run then starts ur container on demand to handle requests and ensures that all incoming requets are handled by dynamically adding n removing containers

cuz cloud run is serverless it means that u as a developer can focus on building your application and not on building nd maintaining the infrastructure that powers it 

container based workflow: in some use cases is better cuz
it provides transparency 
flexibilty

sometimes we r just looking for a way to turn source code into an HTTPS endpoint and we want vendor to make sure your container image is secure well configured and built in consistent way
with cloud run we can use both conatiner n source based workflow 

source based workflow:will deploy source code instead of container image 
cloud run then builds the source and packages application into a container image 
cloud run does this using buildpacks an open source project
cloud run handles HTTPS serving for you 
that means we only have to worry abt handling web requests and you can let cloud run take care of adding the encryption 
the pricing model on cloud run is unique as you only oay for the system resource you use while container is handling web requests for startup n shutdown 

there is small fee for every 1 million requests u serve
the price of conatiner time increases with cpu n memory 
a container with more vcpu and memory is more expensive 
we can use cloud run to run any binary as long as its compiled for linux sixty four bit

means we can use cr to run web app written using proper lang 

