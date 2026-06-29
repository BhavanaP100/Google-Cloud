gc has storage option for structured , unstructed , transcational and relational data
gc has 5 storage options:
cloud storage
cloud sql
spanner
firestore
and
bigtable



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