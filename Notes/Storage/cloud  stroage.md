


1.cloud Storage: a service that offers developers and it organizations durable n highly available object storage.
object storage is a comp data storage architecture that manages data as objects n not as a file n folder hirerachy(file storage) or as chunks of disk(block storage)
these obj are stored in packaged format which contains:binary form of actual data itself
relevant associated meta data
globally unique identifier


These unique keys are in form of urls which means obj storage interacts well with web tech
data is stored in pictures vedios n audio recordfings

cloud storage is googles obj storage product that allows customers to store any amount of  data n to retireve it as often as needed 
its a fully managed scalable service that has a wide variety of uses 
ex: website content , Archival n disaster recover n direct download

cloud storage primary use is 
binary large-obj blob storage is needed for
 online content such as vedio n photos 
 backup n archiving 
 storage of intermediate results 
 
 cloud storage is organised in buckets 
 A bucket needs a globally unique name n a specific geographic loaction for where it shld be stored n ideal location a bucket is where latecny is minimized
 for example: if most users are in europe u probably want to pick a euproean location so:
 gc region is europe or the EU multi region

 the storage obj offered by cloud storage are immutable means we cannot edit but new version is created with every change 
 administrators hv the option to either allow each new version to completely overwrite the older one / to keep track of each change made to a particular obj by enabling "versioning"
 versioning is choosen then cloud storage keep detailed history of modification  made . n with this we can list archived version n restore an obj to an older state / permanently delete a version of an obj as needed
 controlling acces to stored data is essential to ensure security n privacy 
 using IAM roles n where needed access control lists(ACls), organiztion can conform  to security the best practices which require each user to have access n  permissions to only the resources they need to do their jobs n no more than that 
 there are options to control user access to obj n buckets :
 for most purposes,IAM is sufficient 
 if u need finer control u can create ACLs it has scope n permission scope like who can acess n perform an action , permission wt asking can be performed 
cuz storing n retriving large amt of obj data can quickly become expensive cloud storage offers lifecycle policies 

there are 4 primary storage classes in cloud storage 
1.standard storage : best for frequently accesed data n great for storing data for  long time 
2.nearline storage: sstorinf infrequently accesed data like reading / modifying on avg once a mnth or less  eg: data backups long tail multimedia content n data archiving 
3.Cloadline storage : lost cost option for storing infrequently acessed data  meant for readin / modifying  data atmost once every 90 days 
4.Archive  storage : lowest-cost option ideal for data archiving , online backup n disaster recovery, best for accesss less than once a year 

for all 4  storage classes :
unlimited storage 
worlwide accessible 
low latency n high durablility
uniform experiencegeo redudancy 

Cloud storage also provides feature autoclass which automatically transitions 
moves data that is not accesses to colder storage classes to reduce storage cost 
moves data that is accessed to standard storage to optimizze future access

autoclass simpliefies n automates cost saving for ur cloud storage data 
cloud storage has no min fee cuz u pay only for wt u use n prior provisioning , encryots data on server side n use https/tls 

many customers carry out their own online transfer using gcloud storage which is cloud storage command from cloud sdk ,data can also be moved in by drag n drop option in cloud console if accessed through google chrome web browser 

storage tranfer services enables to import large amt of online data into cloud storage n it lets u sechedule n manage batch transfers to cloud storage  from another cloud provider from diff cloud storage region or fm an HTTP(S) endpoint  

tranfer appliance , which is rackable, high capacity storage server that u lease fm gc  we can connect to n/w load it data n then ship it to an upload facility where data is uploaded to cloud storage  we can tranfer up to petabyte of data on single apllicance 