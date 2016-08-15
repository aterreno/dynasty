Meanwhile, back at the ranch...

So assuming you've created a table in DynamoDB (either programmatically with
**Dynasty** or manually in the AWS console) we can get an object representing
that *Table* to put items into that table, get items from that table, and
perform any other operations on that table.

So let's say we have a DynamoDB table already created called UserData and we
want to retrieve an item from it.

```js
var dynasty = require('Dynasty')(credentials),
    // Retrieve an instance of the UserData Table
    users = dynasty.table('UserData');
```

Now we can query it:

```js
// This will look in the UserData table, returning the item with a Hash key that
// matches 'victorquinn'
var promise = users.find('victorquinn');
```

Note, for this library I've chosen to use a Mongo-style syntax here, rather than the DynamoDB names. This is because:

1. I find it more natural and more clean
1. Other developers coming to Dynamo will probably find it more natural
1. If moving to/from DynamoDB this should ease the transition quite a bit.

Also note, we're not passing it a callback. We can, but we don't need to because
**Dynasty** has promise support baked in!

**Dynasty** will also accept a callback function as an optional argument though!
