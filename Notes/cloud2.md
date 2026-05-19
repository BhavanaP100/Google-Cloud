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
   globally unique , assigned by gc n immutable .

### Resource manager tool
is used by google to keep track of resources
its an api that can gather a list of all projects associated with an account,create update delete projects also can recover deleted projects and can be accessed through rpc api n rest api


level 3 google folders
the resources in folder inherit policies and permisiions assigned to the folder 
2 different project monitored by same team u can put policy in common folder where both can acess same policies or if its different then individually in each project folder u can add their policies
to use folder organization node is must

### IAM(identity and access management):

Admininstrator can apply policies that define who can do what on which resources 
 who can be 
google account,google group ,service account,cloud identity domain
who is also called  principal
each principal has its own identifier , usually an email address
can do what part of iam policy is defined by role
IAM role is collection of principal ,whern u grant a role to principal u grant all perimissions that role contians

when principal is given role on specific element of the resource hirerachy the resulting policy apllies to both choosen element n all elements below it in the hirerachy

Iam always checks relevant deny policies before checking relevant allow policies

*** 3 roles in iam**
1. Basic : when applied to project affect all resources ->
   Owner,editor ,veiwer,billing admin

2. predefined:specific google cloud service offer sets of predefined roles and they define where those role applied
3. Custom:to assign role that has even more specific permissions