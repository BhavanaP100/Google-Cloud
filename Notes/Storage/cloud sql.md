Google clouds second core storage option in cloud sql
cloud sql offers fully managed relational databases, including mysqlm postgresql n sql server as a service
its designed hand off mundane but necessary n often tme consuming tasks to google like applying pateches n updates managing backups , and confifuring replications 
features :
doesnt require s/w installation n maintenance
can scale up to 128 processor cores , 864 GB RAM , and 64TB of storage 
supoorts automatic  replication scenarios
suppports  managed backup the cost of an instance covers 7 backuos
encrypts customer data when on googles internal m/w n when stored in db tables,temproary files n backups
includes a n/w firewall 

benefit od cloud sql instances is: are accessible by other google cloud services, n even external services 
it can be used with app engine using standard drivers like connector/J for java  or mysqldb for phython
compute engine instance can be authorized to  access cloud sql instances n configure the cloud sql to be in same zone as ur vm 
cloud sql also suppirts other applications n tools like sql workbench ,toad n other external app using standard mysql drivers.