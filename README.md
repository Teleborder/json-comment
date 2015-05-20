json-comment
------------

Write comments in JSON files by putting them in the data stream.
It's not a Good Thing, but it makes `JSON.parse` compliant files.

### Usage

```javascript

var jsonComment = require('json-comment');

var json = {
  hello: "world"
};

json = jsonComment.write(json, "This is my first JSON file.");
json = jsonComment.write(json, "It's quite good, don't you think?");

console.log(json);

// {
//   "hello": "world",
//   "__comments": [
//     "This is my first JSON file.",
//     "It's quite good, don't you think?"
//   ]
// }

console.log(jsonComment.read(json));

// This is my first JSON file.
// It's quite good, don't you think?

console.log(jsonComment.strip(json));

// {
//    "hello": "world"
// }

```

### Installation

```
$ npm install json-comment
```
