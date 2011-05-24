# What is a toddick?

A toddick is a JavaScript object that sends and receives asynchronous messages. 

Toddicks are a way to write asynchronous code for [node.js][] without using deeply nested 
JavaScript callbacks.

Toddicks implement an [actor][] programming model with a framework similar to the one 
provided by [Erlang][]. 

The following is an example toddick. It produces output each time it receives an `SAY_HELLO` 
message. The `hello_world.SAY_HELLO()` code asynchronously sends the `SAY_HELLO` message to the
toddick.

```js
var toddick = require('toddick');

var HelloWorld = toddick(
  {
    SAY_HELLO: function() {
      console.log('hello async world!');
    }
  }
);

var hello_world = new HelloWorld();

hello_world.SAY_HELLO();   // this call is async
```

The word *toddick* means a very small quantity of something. The name is appropriate because 
toddick based progams typlically concist of many different kinds of small, simple, and highly 
focused toddicks cooperating to perform complex tasks.

Next steps:

 * [Getting Started](https://github.com/maimedleech/toddick/wiki/Getting-Started)
 * [User Guide](https://github.com/maimedleech/toddick/wiki/User-Guide)


[node.js]: http://nodejs.org
[actor]:   http://en.wikipedia.org/wiki/Actor_model
[Erlang]:  http://www.erlang.org/

