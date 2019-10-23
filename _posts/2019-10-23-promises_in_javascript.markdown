---
layout: post
title:      "Promises in Javascript"
date:       2019-10-23 20:19:26 +0000
permalink:  promises_in_javascript
---


Hey, today I decided to write abit of a technical post about Promises in Javascript.

So a Promise in Javascript is intuitively similar to a real Promise, it will either be fulfilled or not, so a Promise in Javascript accepts a callback function that takes two arguments, resolve & reject, you can pass data to resolve and reject that can be used later:

```
let promiseToDoSomething = new Promise(function(resolve, reject) {

});
```

So that's the basic structure of a Promise, now lets take a look on how it works, 

```
let promiseToDoSomething = new Promise(function(resolve, reject) {
      //Doing Something

      let didSomething = true
     
      if(didSomething){
              resolve("We did something");
      } else {
               reject("We failed to do something");
      }
});
```

As an example the Promise is "Doing Something" and then based on if it did it or not it sets didSomething to true/false (in our case its always true in this example) and based on that it will either resolve or reject the Promise.

When we executed the promise you have to wait for it to resolve/reject and there are two methods that can be ran based on if the Promise was resolved or rejected: then & catch that both accept callback functions:

```
promiseToDoSomething.then(function(fromResolve){
    console.log(fromResolve)
}).catch(function(fromReject){
    console.log(fromReject) 
});
```

So as you can see here both the callback functions in then and catch are getting the data that we passed in resolve/reject and logging it to the console, so if the promise has been fulfilled it wil log "We did something" and if it hasn't then it will log "We failed to do something".

You might've worked abit with promises if you were using fetch and it follows the same pattern, when I was creating my project I just wanted to understand Promises abit more indepth and I decided to share the general idea here.

For more on Promises you can check the official MDN documentation [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise).






