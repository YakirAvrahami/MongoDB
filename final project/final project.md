name: Yakir Avrahami    יקיר אברהמי
ID: 307845685
Course Name: הנדסאי תוכנה סייבר אריאל

* my mognodb isn't in the path. i add with the command '''set PATH=%PATH%;C:\Program Files\MongoDB\Server\4.0\bin'''.
* I running the server with '''mongod'''.
* I open a new CMD, and writing '''mongo'''.


1. '''
use mongo_practice
switched to db mongo_practice
'''

2. '''
db.createCollection("movies")
{ "ok" : 1 }
'''

'''
db.movies.insert([
    {
        "title" : "Fight Club",
        "writer" : "Chuck Palahniuk",
        "year" : 1999,
        "actors" : [
        "Brad Pitt",
        "Edward Norton"
        ]
    },
    {
        "title" : "Pulp Fiction",
        "writer" : "Quentin Tarantino",
        "year" : 1994,
        "actors" : [
        "John Travolta",
        "Uma Thurman"
        ]
    },
    {
        "title" : "Inglorious Basterds",
        "writer" : "Quentin Tarantino",
        "year" : 2009,
        "actors" : [
        "Brad Pitt",
        "Diane Kruger",
        "Eli Roth"
        ]
    },
    {
        "title" : "The Hobbit: An Unexpected Journey",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit"
    },
    {
        "title" : "The Hobbit: The Desolation of Smaug",
        "writer" : "J.R.R. Tolkein",
        "year" : 2013,
        "franchise" : "The Hobbit"
    },
    {
        "title" : "The Hobbit: The Battle of the Five Armies",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness."
    },
    {
        "title" : "Pee Wee Herman's Big Adventure"
    },
    {
        "title" : "Avatar"
    }
])
BulkWriteResult({
        "writeErrors" : [ ],
        "writeConcernErrors" : [ ],
        "nInserted" : 8,
        "nUpserted" : 0,
        "nMatched" : 0,
        "nModified" : 0,
        "nRemoved" : 0,
        "upserted" : [ ]
'''

3. '''
db.movies.find().pretty()
{
        "_id" : ObjectId("5c3d8a560aa627cb6d01ae8a"),
        "title" : "Fight Club",
        "writer" : "Chuck Palahniuk",
        "year" : 1999,
        "actors" : [
                "Brad Pitt",
                "Edward Norton"
            ]
}
{
        "_id" : ObjectId("5c3d8a560aa627cb6d01ae8b"),
        "title" : "Pulp Fiction",
        "writer" : "Quentin Tarantino",
        "year" : 1994,
        "actors" : [
                "John Travolta",
                "Uma Thurman"
            ]
}
{
        "_id" : ObjectId("5c3d8a560aa627cb6d01ae8c"),
        "title" : "Inglorious Basterds",
        "writer" : "Quentin Tarantino",
        "year" : 2009,
        "actors" : [
                "Brad Pitt",
                "Diane Kruger",
                "Eli Roth"
            ]
}
{
        "_id" : ObjectId("5c3d8a560aa627cb6d01ae8d"),
        "title" : "The Hobbit: An Unexpected Journey",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit"
}
{
        "_id" : ObjectId("5c3d8a560aa627cb6d01ae8e"),
        "title" : "The Hobbit: The Desolation of Smaug",
        "writer" : "J.R.R. Tolkein",
        "year" : 2013,
        "franchise" : "The Hobbit"
}
{
        "_id" : ObjectId("5c3d8a560aa627cb6d01ae8f"),
        "title" : "The Hobbit: The Battle of the Five Armies",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness."
}
{
        "_id" : ObjectId("5c3d8a560aa627cb6d01ae90"),
        "title" : "Pee Wee Herman's Big Adventure"
}
{ 
        "_id" : ObjectId("5c3d8a560aa627cb6d01ae91"), "title" : "Avatar"
}
'''

4. '''
db.movies.find({"writer":"Quentin Tarantino"}).pretty()
{
        "_id" : ObjectId("5c3df4ad9975314297af9371"),
        "title" : "Pulp Fiction",
        "writer" : "Quentin Tarantino",
        "year" : 1994,
        "actors" : [
                "John Travolta",
                "Uma Thurman"
        ]
}
{
        "_id" : ObjectId("5c3df4ad9975314297af9372"),
        "title" : "Inglorious Basterds",
        "writer" : "Quentin Tarantino",
        "year" : 2009,
        "actors" : [
                "Brad Pitt",
                "Diane Kruger",
                "Eli Roth"
        ]
}
'''

5. '''
db.movies.find({"actors":"Brad Pitt"}).pretty()
{
        "_id" : ObjectId("5c3df4ad9975314297af9370"),
        "title" : "Fight Club",
        "writer" : "Chuck Palahniuk",
        "year" : 1999,
        "actors" : [
                "Brad Pitt",
                "Edward Norton"
        ]
}
{
        "_id" : ObjectId("5c3df4ad9975314297af9372"),
        "title" : "Inglorious Basterds",
        "writer" : "Quentin Tarantino",
        "year" : 2009,
        "actors" : [
                "Brad Pitt",
                "Diane Kruger",
                "Eli Roth"
        ]
}
'''

6. '''
db.movies.find({"franchise":"The Hobbit"}).pretty()
{
        "_id" : ObjectId("5c3df4ad9975314297af9373"),
        "title" : "The Hobbit: An Unexpected Journey",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit"
}
{
        "_id" : ObjectId("5c3df4ad9975314297af9374"),
        "title" : "The Hobbit: The Desolation of Smaug",
        "writer" : "J.R.R. Tolkein",
        "year" : 2013,
        "franchise" : "The Hobbit"
}
{
        "_id" : ObjectId("5c3df4ad9975314297af9375"),
        "title" : "The Hobbit: The Battle of the Five Armies",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness."
}
'''

7. '''
    db.movies.find({$and :[{"year":{$gt:1900}},{"year":{$lte:1999}}]}).pretty()
{
        "_id" : ObjectId("5c3df4ad9975314297af9370"),
        "title" : "Fight Club",
        "writer" : "Chuck Palahniuk",
        "year" : 1999,
        "actors" : [
                "Brad Pitt",
                "Edward Norton"
        ]
}
{
        "_id" : ObjectId("5c3df4ad9975314297af9371"),
        "title" : "Pulp Fiction",
        "writer" : "Quentin Tarantino",
        "year" : 1994,
        "actors" : [
                "John Travolta",
                "Uma Thurman"
        ]
}
'''

8. '''
db.movies.find({$or :[{"year":{$gte:2000}},{"year":{$lte:1989}}]}).pretty()
{
        "_id" : ObjectId("5c3df4ad9975314297af9372"),
        "title" : "Inglorious Basterds",
        "writer" : "Quentin Tarantino",
        "year" : 2009,
        "actors" : [
                "Brad Pitt",
                "Diane Kruger",
                "Eli Roth"
        ]
}
{
        "_id" : ObjectId("5c3df4ad9975314297af9373"),
        "title" : "The Hobbit: An Unexpected Journey",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit"
}
{
        "_id" : ObjectId("5c3df4ad9975314297af9374"),
        "title" : "The Hobbit: The Desolation of Smaug",
        "writer" : "J.R.R. Tolkein",
        "year" : 2013,
        "franchise" : "The Hobbit"
}
{
        "_id" : ObjectId("5c3df4ad9975314297af9375"),
        "title" : "The Hobbit: The Battle of the Five Armies",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness."
}
'''

9. '''
db.movies.update({"title" : "The Hobbit: An Unexpected Journey"},{$set: {"synopsis" :"A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug.",}})
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
'''

10. '''
db.movies.update({"title" : "The Hobbit: The Desolation of Smaug"},{$set: {"synopsis" :"The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring.",}})
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
'''

11. '''
db.movies.update({"title" : "Pulp Fiction"},{$push: {"actors" :"Samuel L. Jackson",}})
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
'''

3
12. '''
db.movies.createIndex( { synopsis: "text" } )
{
        "createdCollectionAutomatically" : false,
        "numIndexesBefore" : 1,
        "numIndexesAfter" : 2,
        "ok" : 1
}
'''
'''
db.movies.find( { $text: { $search: "Bilbo" } } ).pretty()
{
        "_id" : ObjectId("5c3df4ad9975314297af9374"),
        "title" : "The Hobbit: The Desolation of Smaug",
        "writer" : "J.R.R. Tolkein",
        "year" : 2013,
        "franchise" : "The Hobbit",
        "synopsis" : "The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."
}
{
        "_id" : ObjectId("5c3df4ad9975314297af9375"),
        "title" : "The Hobbit: The Battle of the Five Armies",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness."
}
{
        "_id" : ObjectId("5c3df4ad9975314297af9373"),
        "title" : "The Hobbit: An Unexpected Journey",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."
}
'''

13. '''
db.movies.find( { $text: { $search: "Gandalf" } } ).pretty()
{
        "_id" : ObjectId("5c3df4ad9975314297af9374"),
        "title" : "The Hobbit: The Desolation of Smaug",
        "writer" : "J.R.R. Tolkein",
        "year" : 2013,
        "franchise" : "The Hobbit",
        "synopsis" : "The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."
}
'''

14. '''
db.movies.find( { $text: { $search: "Bilbo -Gandalf" } } ).pretty()
{
        "_id" : ObjectId("5c3df4ad9975314297af9375"),
        "title" : "The Hobbit: The Battle of the Five Armies",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness."
}
{
        "_id" : ObjectId("5c3df4ad9975314297af9373"),
        "title" : "The Hobbit: An Unexpected Journey",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."
}
'''

15. '''
db.movies.find( { $text: { $search: "Bilbo Dwardes" } } ).pretty()
{
        "_id" : ObjectId("5c3df4ad9975314297af9374"),
        "title" : "The Hobbit: The Desolation of Smaug",
        "writer" : "J.R.R. Tolkein",
        "year" : 2013,
        "franchise" : "The Hobbit",
        "synopsis" : "The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."
}
{
        "_id" : ObjectId("5c3df4ad9975314297af9375"),
        "title" : "The Hobbit: The Battle of the Five Armies",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness."
}
{
        "_id" : ObjectId("5c3df4ad9975314297af9373"),
        "title" : "The Hobbit: An Unexpected Journey",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."
}
'''

16. '''
db.movies.find( { $text: { $search: "gold dragon" } } ).pretty()
{
        "_id" : ObjectId("5c3df4ad9975314297af9373"),
        "title" : "The Hobbit: An Unexpected Journey",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."
}
'''

17. '''
db.movies.remove({"title":"Pee Wee Herman's Big Adventure"})
WriteResult({ "nRemoved" : 1 })
'''

18. '''
db.movies.remove({"title":"Avatar"})
WriteResult({ "nRemoved" : 1 })
'''