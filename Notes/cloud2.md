### Google cloud resource hierarchy
level 1- Resources(vm ,cloudstorage buckets, tables in big query)
level 2-project 
level 3-folder
level 4-organization node(folder,project n resources)

level 2 projects are basis for enabling and using gcp servcies like managing api's enabling biling adding n removing collabrators and enabling other google services
1. each project is separate entities under organization node
2. project hold resources each of which belong to just one project
3. Project can have different owners and users
4. Projects are billed n managed separately
   
Each gcp project has project id project name project number:
1. project Id :
   globally unique, assinged by gc but mutable during creation only.
2. project name:
   can be named by us can repeat
3. project number:
4. globally unique , assigned by gc n immutable .
