## ==MongoDB Commands In Windows==

##### Switch to a database or Create it Database if not exist:
> `> use contact`

##### Show All Databases:
> `> show databases`

##### Create a collection:
> `> db.createCollection("contactlist")`

##### Show All Collections In A Database :
> `> show collections`

> `> db.contactlist.find()`

##### Insert Many Documents In A Collection :
> `> db.contactlist.insertMany([{
"Last name": "Ben Lahmer", "First name": "Fares", "Email": "fares@gmail.com", "age":26
}, {
"Last name": "Kefi", "First name": "Seif", "Email": "kefi@gmail.com", "age":15
}, {
"Last name": "Fatnassi", "First name": "Sarra", "Email": "sarra.f@gmail.com", "age":40
}, {
"Last name": "Ben Yahia", "First name": "Rym", "age":4
}, {
"Last name": "Cherif", "First name": "Sami", "age":3
}])`

##### Remove field from Document:
> `> db.contactlist.update({"age": 15}, {$unset : {"name" : ""}})`

##### Examples:

1. Display all the information about only one person using his id:
> `> db.contactlist.findOne({"_id" :ObjectId("60568b697bba827c02a23320")})`

2. Display all the contact list having age > 18:
> `> db.contactlist.find({age : {$gt : 18}}).pretty()`

3. Display all the contact list having age>18 and name containing "ah":
> `> db.contactlist.find({$and :[{age : {$gt : 18}}, {$or: [{"First name" : /^.*ah.*$/}, {"Last Name" : /^.*ah.*$/}]}]}).pretty()`

4. Change the contact first name of "kefi Seif" by "Kefi Anis":
> `> db.contactlist.updateOne({"First name" : "Seif"}, {$set: {"First name": "Anis"}})`

5. Delete the the contact list having age < 5:
> `> db.contactlist.remove({age : {$lt : 5}})`

6. Display all the contact list:
> `> db.contactlist.find().pretty()`

##### Kais Website:
`MONGO_URI = mongodb+srv://kais:hazard10chelsea@cluster0.z1upl.mongodb.net/TestMyProject?retryWrites=true&w=majority`
`SECRET_KEY = KAISDOSS`
`ADMIN_ONE = s.slimene19@gmail.com`
`ADMIN_TWO = kaisdoss1989@gmail.com`

> `> mongod`

> `> mongo "mongodb+srv://cluster0.z1upl.mongodb.net/myFirstDatabase" -u kais -p hazard10chelsea  --authenticationDatabase admin`

> `> mongo "mongodb+srv://cluster0.z1upl.mongodb.net/" -u kais -p hazard10chelsea  --authenticationDatabase admin`

##### Mock A Slow API:
```js
const res = await fetch('http://slowwly.robertomurray.co.uk/delay/5000/url/https://jsonplaceholder.typicode.com/todos/1')
const data = await res.json()
console.log('Here our response', data)
```
