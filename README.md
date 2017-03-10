<h1>Treehouse Mongo Basics</h1>

<p>
# open the mongo shell
mongo
# switch to your db, for example  "mongoBasics"
> use mongoBasics
# load the seed.js file
> load('./path/to/seed.js')
# check out the data you have!
> db.getCollectionNames()
</p>

<h1>My Notes</h1>

Only works with Homebrew installed
Mongo Hacker installed

run ->
$mongod  - Run in project directory. mongod is the primary daemon process for the MongoDB system. It handles data requests, manages data access, and performs background management operations.

in new tab run ->
$mongo - Use in project directory. launches mongodb shell. Access point to the database.

$use <db> - Switch current database to <db> . The mongo shell variable db is set to the current database.

$show dbs - lists databases that mongo currently has

$db.<>.insert({JSON object}) - db = current database from $use. post = collections. insert = insert

Querying Collections:
$db.<>.find() - list docs in collection
$db.<>.find()[#] - search database
$db.<>.findOne() - returns one document

Examples with parameters:
$db.posts.find({}.{body: false, description: false})
$db.posts.find({},{title: true})
db.users.find({}, {_id: true})
$db.posts.find({title: 'Parenting 101'},{})

$or{} - query operator

$db.find().limit(#) - limits number of documents returned

$Object.keys(db.<>.find()[#]) - returns keys in object

$db.<>.find({}, {title: true}).sort({title: 1}) - will sort titles in alphabetical order
$db.<>.find({}, {title: true}).sort({title: -1}) descending order

$load(./<file.js>) - loads file into mongo

$db.<>.find({},{title: true}).limit(2).skip(2) - will skip first two documents and display next 2

$db.<>.count() - amount of entries

$<>.author - references objectId, can be from another collection

$db.<>.getIndexes()
$db.<>.createIndex({title: 1}, {})
$db.<>.dropIndex('title_1')

$db.<>.update() - update
$db.<>.update({author: ObjectId("58c2a4b7f8bbf8c251da230c")}, {$set: {tags:['foo', 'bar'], title: 'I have been updated'}})
