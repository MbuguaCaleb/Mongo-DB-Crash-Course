# Mongo-DB-Crash-Course

Mongo DB Crash Course

**Implemenatation of Mongo DB**

```
(a)Can be from Local implementation from your machine.Via the GUI once mongo is installed in your system.


(b)ATLAS - May be implemented from The cloud which is a more preferred way as you do not have to worry about any of your MongoDB Implementations.


(c)Compass..Where Compass is a local GUI in your machine that can be used to Manage Mongo.

```

**NOSQL DATABASES**

```
Its a type of a NoSQL database.

Data is not stored in columns and rows.

Data is stored in collections of objects..very similar to Json Objects in Javscript.

It is very popular in the javascript community the MERN Stack.MEAN stack..

Data Structure is Scalable...We have freedom to sturcture or data even in continuos development unlike in relational databases.


(Data is in JSON...APART THAT THERE ARE A FEW MORE DATATYPES)

```

**Advantages**

```
(a)It is very scalable.

(b)Has built in replication and shutting

(c)It scales horizantally..


A big advantage of Mongo is that you do not have to make an initial map of the database..
You are free to structure data however we wat through our application

```

**Concepts**
```
A collection in MongoDB is similar to a table.It is used to collect or hold a set of
data.
You can put anytype of data in a document and in any way you want.

Find in Mongo is like where in the normal sql queries.

Upsert means the following:If you do not find a record when selcting then insert.

We have operators which are like functions that can do summation of rows and columns etc.

find() with no parameters returns all of your values.


```

**SUBDOCUMENTS**
```
How do you implement relationships within Mongo DB classes..

In a relational database you use foreign keys to interlink your data.

In Mongo However,you append all of your data into the same object...You can create also a separate collection for your related data but the best approach is the use of subdocuments within MongoDB..

You can have two dictionaries in a list.


Insert document is the same as insert data to the collection.
```


**CLI Commands in Mongo**


## Show All Databases
```
show dbs
```
## Show Current Database
```
db
```
## Create Or Switch Database
```
use acme
```
## Drop
```
db.dropDatabase()
```
## Create Collection
```
db.createCollection('posts')
```
## Show Collections
```
show collections
```
## Insert Row
```
db.posts.insert({
  title: 'Post One',
  body: 'Body of post one',
  category: 'News',
  tags: ['news', 'events'],
  user: {
    name: 'John Doe',
    status: 'author'
  },
  date: Date()
})
```
## Insert Multiple Rows
```
db.posts.insertMany([
  {
    title: 'Post Two',
    body: 'Body of post two',
    category: 'Technology',
    date: Date()
  },
  {
    title: 'Post Three',
    body: 'Body of post three',
    category: 'News',
    date: Date()
  },
  {
    title: 'Post Four',
    body: 'Body of post three',
    category: 'Entertainment',
    date: Date()
  }
])
```
## Get All Rows
```
db.posts.find()
```
## Get All Rows Formatted
```
db.find().pretty()
```
## Find Rows
```
db.posts.find({ category: 'News' })
```
## Sort Rows
```
# asc
db.posts.find().sort({ title: 1 }).pretty()
# desc
db.posts.find().sort({ title: -1 }).pretty()
```
## Count Rows
```
db.posts.find().count()
db.posts.find({ category: 'news' }).count()
```
## Limit Rows
```
db.posts.find().limit(2).pretty()
```
## Chaining
```
db.posts.find().limit(2).sort({ title: 1 }).pretty()
```
## Foreach
```
db.posts.find().forEach(function(doc) {
  print("Blog Post: " + doc.title)
})
```
## Find One Row
```
db.posts.findOne({ category: 'News' })
```
## Find Specific Fields
```
db.posts.find({ title: 'Post One' }, {
  title: 1,
  author: 1
})
```
## Update Row
```
db.posts.update({ title: 'Post Two' },
{
  title: 'Post Two',
  body: 'New body for post 2',
  date: Date()
},
{
  upsert: true
})
```
## Update Specific Field
```
db.posts.update({ title: 'Post Two' },
{
  $set: {
    body: 'Body for post 2',
    category: 'Technology'
  }
})
```
## Increment Field (\$inc)
```
db.posts.update({ title: 'Post Two' },
{
  $inc: {
    likes: 5
  }
})
```
## Rename Field
```
db.posts.update({ title: 'Post Two' },
{
  $rename: {
    likes: 'views'
  }
})
```
## Delete Row
```
db.posts.remove({ title: 'Post Four' })
```
## Sub-Documents
```
db.posts.update({ title: 'Post One' },
{
  $set: {
    comments: [
      {
        body: 'Comment One',
        user: 'Mary Williams',
        date: Date()
      },
      {
        body: 'Comment Two',
        user: 'Harry White',
        date: Date()
      }
    ]
  }
})
```
## Find By Element in Array (\$elemMatch)
```
db.posts.find({
  comments: {
     $elemMatch: {
       author: 'Mary Williams'
       }
    }
  }
)
```
## Add Index
```
db.posts.createIndex({ title: 'text' })
```
## Text Search
```
db.posts.find({
  $text: {
    $search: "\"Post O\""
    }
})
```
## Greater & Less Than
```
db.posts.find({ views: { $gt: 2 } })
db.posts.find({ views: { $gte: 7 } })
db.posts.find({ views: { $lt: 7 } })
db.posts.find({ views: { $lte: 7 } })
```


```
Notes by Mbugua Caleb
```


```
Tututor Brad Travesy

```