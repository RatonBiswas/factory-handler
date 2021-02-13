## What is this?
A handler factory function documents from all the other collections,with one simple function.Adding very similar handlers to all of your controlles,will create a lot of duplicate code,right?All this create handlers, post handlers, update handlers , or all this delete handlers, they really all just look basically the same , right? 
Also imagine that we wanted to change, like some https status code or status message, then we would have to go into each and every contollers, and then change all the handlers in there and so , instead of manually writing all these handlers why not simply create a factory function that's gonna return these handlers for us.So a factory function is exactly that it's a function that returns another function and is this case our handler function , so for deleting , for updating , for creating, and for reading resources.For every single model that we have in our application and that we might have in the future, So this function need to be prepared for that and so what that means is that inside the factory function we will pass in the model , so we pass the model and then we create a new function and that function will right away then return our async function.
## Installation
Run `npm i factory-handler --save`
## How To Use
Use : 
```
const Model =  require('MongooseModel') // Here MongooseModel Is Your Schema File.

const factory = require('factory-handler')

exports.getAllModelPost = factory.getAll(Model) // Here Model Is Your Mongoose Schema Name.
exports.createModelPost = factory.createOne(Model)
exports.getModelPost = factory.getOne(Model)
exports.updateModelPost = factory.updateOne(Model)
exports.deleteModelPost = factory.deleteOne(Model)
```

## User Manual 
```
const User = require('../models/userModel')
const factory = require('factory-handler')


exports.getAllUserPost = factory.getAll(User)
exports.createUserPost = factory.createOne(User)
exports.getUserPost = factory.getOne(User)
exports.updateUserPost = factory.updateOne(User)
exports.deleteUserPost = factory.deleteOne(User)

```

## Parameters
The Handler Factory accepts one parameters, Model name value and Model is your mongoose schema name.

