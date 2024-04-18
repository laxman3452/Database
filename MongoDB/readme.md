**What is a SQL?**
-> SQL stands for Structured Query Language which is used to handle data in a Relational Database Management Systems(RDMS like MySQL, PostgreSQL,Oracle,Microsoft SQL Server e.t.c)

**What is a MongoDB?**
-> MongoDB is a NoSQL DBMS which is used to store data in json like format.


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