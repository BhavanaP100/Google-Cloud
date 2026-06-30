gc has storage option for structured , unstructed , transcational and relational data
gc has 5 storage options:
cloud storage
cloud sql
spanner
firestore
and
bigtable

comparison:         best for                      |  capacity
cloud storage : storing immutable blobs lagrer than 10 mb and petabytes max unit size: 5TB per  obj
cloud sql : fullsql support for online transaction processing system n web frameworks n existing appl , upto 64TB
spanner: fullsql support for online transaction processing system n horizontal scalibilty , petabytes
firestore : massive scaling and predictability togetherwith real time query results n offline query support , tera bytes : max unit size 1 MB per entity 

bigtble : storing large amt of structred objects and does not support sql queries and multi row transastions and analytical data with heavy read n write events , petabytes max unit size 10MB per cell and 100MB per row

bigquery on the edge bwtween data storage n data processing 