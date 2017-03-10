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

<p>Only works with Homebrew installed</p>
<p>Mongo Hacker installed</p>

<p>run -></p>
<p>$mongod  - Run in project directory. mongod is the primary daemon process for the MongoDB system. It handles data requests, manages data access, and performs background management operations.</p>

<p>in new tab run -></p>
<p>$mongo - Use in project directory. launches mongodb shell. Access point to the database.</p>

<p>$use <db> - Switch current database to <db> . The mongo shell variable db is set to the current database.</p>

<p>$show dbs - lists databases that mongo currently has</p>

<p>$db.<>.insert({JSON object}) - db = current database from $use. post = collections. insert = insert</p>

<h3>Querying Collections:</h3>
<p>$db.<>.find() - list docs in collection</p>
<p>$db.<>.find()[#] - search database</p>
<p>$db.<>.findOne() - returns one document</p>

<h3>Examples with parameters: </h3>
<p>$db.posts.find({}.{body: false, description: false})</p>
<p>$db.posts.find({},{title: true})</p>
<p>db.users.find({}, {_id: true})</p>
<p>$db.posts.find({title: 'Parenting 101'},{})</p>

<p>$or{} - query operator</p>

<p>$db.find().limit(#) - limits number of documents returned</p>

<p>$Object.keys(db.<>.find()[#]) - returns keys in object</p>

<p>$db.<>.find({}, {title: true}).sort({title: 1}) - will sort titles in alphabetical order</p>
<p>$db.<>.find({}, {title: true}).sort({title: -1}) descending order</p>

<p>$load(./<file.js>) - loads file into mongo</p>

<p>$db.<>.find({},{title: true}).limit(2).skip(2) - will skip first two documents and display next 2</p>

<p>$db.<>.count() - amount of entries</p>

<p>$<>.author - references objectId, can be from another collection</p>

<p>$db.<>.getIndexes()</p>
<p>$db.<>.createIndex({title: 1}, {})</p>
<p>$db.<>.dropIndex('title_1')</p>

<p>$db.<>.update() - update</p>
<p>$db.<>.update({author: ObjectId("58c2a4b7f8bbf8c251da230c")}, {$set: {tags:['foo', 'bar'], title: 'I have been updated'}})</p>
