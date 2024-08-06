# installation
```BASH
 sudo apt-get install gnupg curl
 curl -fsSL https://www.mongodb.org/static/pgp/server-7.0.asc | sudo gpg -o /usr/share/keyrings/mongodb-server-7.0.gpg --dearmor
 sudo touch /etc/apt/sources.list.d/mongodb-org-7.0.list
 echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-7.0.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/7.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list
 sudo apt-get update
 sudo apt-get install -y mongodb-org
 get apt-get update -y
 sudo apt-get update -y 
 sudo service mongod status
 sudo service mongod start
 sudo service mongod status
 echo "mongodb-org hold" | sudo dpkg --set-selections
 echo "mongodb-org-database hold" | sudo dpkg --set-selections
 echo "mongodb-org-server hold" | sudo dpkg --set-selections
 echo "mongodb-mongosh hold" | sudo dpkg --set-selections
 echo "mongodb-org-mongos hold" | sudo dpkg --set-selections
 echo "mongodb-org-tools hold" | sudo dpkg --set-selections
 sudo service mongod status
 pip3 install pymongo
```


# Introduction
## data type `like a ECMAscript`
- `null`: no value.
- `new Date()`: to add date time data.
- `{name: "name" ... }` add object inside documents.
## command
- `show dbs;`: show databases.
- `use <NameDB>;`:  Select of create database, if you don't create a collection database was not Showing.
- `db.createCollection("<NameOfCollection>")`: create a collection in database.
- `db.dropDatabase()`: delete database.
1. INSERT:
	- `db.<nameCollection>.insertOne(data_json)`: insert one fields. if no collection found well be create it.
	- `db.<nameCollection>.insertMany([data_json ...])`: insert many fields. if no collection found well be create it.

2. SELECT:
	- `db.<nameCollection>.find()`: select all data from Collection.
	- `db.school.find({name: "Holberton school"}).forEach(printjson);` : search specific data.
	- `db.school.find().sort(<namefield>: [1: ASC OR -1:DESC])`: select with order ASC, DESC.

3. UPDATE: `SET OR UNSET`
	- `db.school.update({mention data}, {"$set": {update or create}}, {multi: true or false});`
	- `db.school.update({mention datat}, {"$unset": {delete data: ""}})`

4. DELETE:
	- `db.school.delete()`