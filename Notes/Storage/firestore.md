firestore is flexible , horizontally scalable n NoSql cloud db for mobile , web n server development 
with firestore , data  is stored in documents n then organized in collection
firestore Nosql queries can be then used to retrieve individual , specific documents 
retrieve all doc in a collection that match ur query paramters 
can include multiple,chained filters 
can combine filtering and sorting options 
indexed by default
firestore uses data synchronization to update data on any connected device 
its also desgined to make simple,one time fetch queries efficiently 
it caches data that an app is actively using so app can read write listen to n query even if device is offline
when device is back online firestore synchronizes any local changes back 

firestore leverages gc powerful infra:
automatic multi region data replication 
strong consistency gurantees
atomic batch operations 
real transaction support 
