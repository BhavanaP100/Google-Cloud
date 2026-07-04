 many application contain event driven parts for eg appliation that lets user upload images 
 when  that event takes place the image might need to be processed in few different ways like converting image to standard format
 converting a thumbnail into different sizes 
 and storing each new file repository 
 this function could be integrated into application but then ud have to provide compute resources for it whether it happens once a millisecond or once a day
 with cloud run functions you write a single purpose function 
 that completes the necessary image manipulations and arrange it to automatically run whenever a new image is uploaded 
 cloud run functions is a lightweight event based asynchronous compute solution that allows u to create small single purpose function that respond to cloud events without need to manage a server or a runtime environment 
 to contruct appl workflows from individual business logic tasks and connect and extend cloud services 
billed to nearest 100 ms n only while ur code is running
supports wrting code in n no. of lang 
events from cloud storage and pub/sub can trigger cloud run functions asynchronously or use http invocation for synchronous execution 