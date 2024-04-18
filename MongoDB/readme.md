**What is a SQL?**
-> SQL stands for Structured Query Language which is used to handle data in a Relational Database Management Systems(RDMS like MySQL, PostgreSQL,Oracle,Microsoft SQL Server e.t.c)

**What is a MongoDB?**
-> MongoDB is a NoSQL DBMS which is used to store data in json like format.


 **MySQL and MongoDB differences**
 Database    Database
 Document    Table
 Entity      Collection
 index       index
 _id field   Primary Key
 Field       Column
 Embedding   Join
 Aggregation GROUP BY

**imp**
--MongoDB doesn't supports transaction and ACID principals i.e there is no consistency of data in NoSQL.
--SQL supports transaction and ACID principals and there is consistency and integrity of data in a database.



**What is a Schema in a MongoDB/Any other database?**
-> A Schema is a blueprint of structure, like name field will contain string like that.


**imp**
Biggest flexibility of mongoDB over Mysql is that we can add extra field for any collection in mongoDB but in SQL, we need to redesign the whole table structure and tables also if needed.




**Three A of mongoDB**
Application
Analytics
Admin


**Create Operation in MongoDB**
insertOne({data},options)
insertMany([{data},{data}],options)

e.g
insertOne({
    "name":"Alex",
    "salary":"$1000"
})

insertMany([
    {
    "name":"Alex",
    "salary":"$1000"
    },
    {
    "name":"Rodriguez",
    "salary":"$2000"
    }
])



**Read Operations in MongoDB**

findOne({filter},options)
findMany({filter},options)


e.g:- 
findOne({name:"hari})
findMany({salary: "$1000"})


**Update Operations in MongoDB**

updateOne({filter},{data},options)
updateMany({filter},{data},options)

e.g:-

updateOne({name:"hari"},{$set :{isActive:true}})
updateMany({name:"hari"},{$set:{isActive:true}})

<!-- Here $set is a atomic operator -->


**Delete Operations in MongoDB**

deleteOne({filter},options)
deleteMany({filter},options)

e.g:-
deleteOne({name:"hari"})
deleteMany({}) //Deletes all


**Find Operations**
find({count : {$gt:1}}).pretty()


**DAtabase issues with update in MongoDB**
use updateOne,updateMany instead of update

updateOne({name:"hari"},{courseCount:2}) 
<!-- Doesn't runs without $set atomic operator. -->
update({name:"hari"},{courseCount:2})
<!-- Runs but deletes all pre-stored fields and adds only courseCount in this collection. -->

**Getting more data in MongoDB**
insertMany([{},{},....])

find().pretty()
Type it for more.

find().forEach((item) => {
    if(item.name === "hari") printjson(item)
})

We don't fetch entire database at once. It's better to filter out or receive less data from the databsase.

**Save Bandwith while querying in MongoDB**
find({},{name:1,_id:0,salary:0})
<!-- Only outputs the email only -->
find({},{name:1,_id:0,salary:0}).toArray()

find({filter},{name:1,_id:0,salary:0}).forEach(()=>{})



**Understanding Objects structure in MongoDB**

{
    "_id":"",
    "name":"ok",
    "profilePic":{
        "small":"250px",
        "medium":"350px",
        "large":"450px"
    }
}
find({profilePic.small:"250px"})
<!-- Use Multiple . to get inside more -->


**Understanding Arrays in MongoDB**
updateOne({_id:""},{$set : {"login":["sunday","Tuesday","Friday"]}})

find({_id:""}).login 
<!-- invalid because we can't show for multiple collections -->

findOne({_id:""}).login 
<!-- Works -->


**Database Modeling**
 cosider ebook 
 --Database Design for mere mortals

 **Relations in mongoDB**
 one-one
 one-many
 many-many

