#### overview

These methods act on **Items** within a **Table**.

As such, for all the following examples, we'll assume:

1. That the setup has been, so there's a dynasty object with the credentials
2. That the tables we're accessing have already been created, unless otherwise
   specified
3. That there is a table object already created for each table

In other words, we're going to assume the following code has been run already:

```js
var credentials = {
    accessKeyId: process.env.AWS_ACCESS_KEY_ID,
    secretAccessKey: process.env.AWS_SECRET_ACCESS_KEY
};

var dynasty = require('dynasty')(credentials);

// A table of countries with a hash key of *name*
var lands = dynasty.table('Lands');

// A table of counties with a hash key of *land* and a range key of *name*
var counties = dynasty.table('Counties');
```

We will use `lands` and `counties` as examples below.

This top-level overview is to help cut down on the repetition below.
