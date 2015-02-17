mqemitter-mongodb&nbsp;&nbsp;[![Build Status](https://travis-ci.org/mcollina/mqemitter-mongodb.png)](https://travis-ci.org/mcollina/mqemitter-mongodb)
=================

MongoDB powered [MQEmitter](http://github.com/mcollina/mqemitter).

See [MQEmitter](http://github.com/mcollina/mqemitter) for the actual
API.

Install
-------

```bash
$ npm install mqemitter-mongodb --save
```

Example
-------

```js
var mongodb = require('mqemitter-mongodb')
  , mq    = mongodb({
        port: 12345
      , localhost: 12.34.56.78
      , password: 'my secret'
      , db: 4
    })
  , msg   = {
        topic: 'hello world'
      , payload: 'or any other fields'
    }

mq.on('hello world', function(message, cb) {
  // call callback when you are done
  // do not pass any errors, the emitter cannot handle it.
  cb()
})

// topic is mandatory
mq.emit(msg, function() {
  // emitter will never return an error
})
```

Acknowledgements
----------------

Code ported from [Ascoltatori](http://github.com/mcollina/ascoltatori).

License
-------

MIT
