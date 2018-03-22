# node.js
How to create a new collection in node.js using Mongodb in version 3.6.3
var MongoClient=require('mongodb').MongoClient; //Mongodb module
var assert=require('assert');//assert will help us in handling the errors
var url = "mongodb://localhost:27017/";
MongoClient.connect(url, function(err, db) {   
    if (err) throw err;
    var dbase = db.db("mydb"); //here
    dbase.createCollection("customers", function(err, res) {
        if (err) throw err;
        console.log("Collection created!");
        console.log(res); 
        db.close();  
    });
});
