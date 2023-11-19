

# commands


mongosh


exit

cls

show all current databases
show dbs

to select current db or create a new one. 
use <dbname>

use school

db won't show yet.


db.createCollection("collection name such as students")


show all records:

db.students.find()

school> 
shows you are in current db

current connected db will drop
db.dropDatabase()

structure of mongo:

database [ collection1 collection2 collection3]

collection1 [ {name : "xd", id : 1}, {name : "Tony", id = 2}]

collection1 [ document1, document2 ]



collection will be created if one doesnt exist
insert
db.students.insertOne({name: "Spongebob", age:30, gpa:3.2})

find all documents in student
db.students.find()


db.students.insertMany([{name:"Patrick", age: 38, gpa:1.5},{name:"Sandy", age:27, gpa:4.0},{name: "Gary", age:18, gpa:2.5}])

db.students.insertOne({name:"larry", age:50, gpa:3.2, fulltime: false, registerDate: new Date(), graduationDate: null, courses: ["biology", "chemestry", "calculus"], address: {street : "123 main street", city: "Bikini Bottom", zip: 12345}})

new Date("2023-01-01")

new Date() without any args will be current time. 


arrays and documents within documents are allowed.

keys do not need quotes. 





sorting and limiting documents


db.students.find()

db.students.find().sort({name : 1})
db.students.find().sort({gpa:1})

this is called method chaining

1 = alphabetical order (lowest to highest)
-1 = reverse alphabetical order (highest to lowest.)



from 22:35


db.students.find().sort({gpa:-1}).limit(1)

find highest gpa


db.students.find().sort({gpa:1}).limit(1)

find lowest gpa



db.students.find().sort({gpa:-1}).limit(3)
find top 3 gpa


db.students.find().limit(2)
find 2 first documents 



find command


similar to where clause in SQL
db.students.find({name:"Spongebob"})

db.students.find({fulltime:false})


db.students.find({fulltime:false, gpa:4.0})


26.49



db.students.find({}, {name:1})
show all student but only name field. Called a projection parameter. 



db.students.updateOne({name:"Spongebob"}, {$set:{fulltime:true}})

db.students.updateOne({name:"Spongebob"}, {$unset:{fulltime:""}})