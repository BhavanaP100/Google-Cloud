bigtable is nosql big data db service its same db that powers maby core google services , including search , analytics , maps n gmail 
bigtable is desgined to handle massive workloads at consistent low latency n high throughput , so its great choices for both operational n anlytical applications , including internet of things,user analaytics n financial data analysis

customers choose bigtable of:
they work with more than 1TB of semi structured data
data is fast with high throughput or its rapidly changing 
they work with noSql data 
data is time series or has natural sematic ordering 
they work with big data running asynchronous batch or synchronoys real time processing on the data 
they run machine learning algo 


bigtable can interact with other gc service n third party clients 
using api data can be read from n written to bigtable through a data service layer like managed vm , the HBase REST Server or a java server using HBase client 
data can also be streamed in through a variety of popular stream frameworks like 
dataflow streaming , spark streaming n storm 

and data can also be read from n written to bigtable  through batch processes like hadoop mapreduce , data flow or spark 
the new daa is written back to bigtable or to downstream db 