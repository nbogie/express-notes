# Express Cheatsheet

## A minimal server with 4 lines of code

```
//load the 'express' module which makes writing webservers easy
const express = require('express');

const app = express();

app.get('/', function(request, response) {
  response.send("hello Express world!")
});

//Start our server so that it listens for HTTP requests!
app.listen(process.env.PORT);
```


## Adding a "Route"

A route is simply a path and HTTP method that the server can handle so:

```js
app.get('/', function(request, response) {
  response.send("hello Express world!")
});
```

The above shows a 'route handler' being registered which will be used to handle a client HTTP GET request to the '/' path.  It will respond with the string (text) "hello Express world!"

* Notice the `app.get` in the beginning - this determines the method for this route.  Other common methods include 'post', 'put', and 'delete'.

* Calling `app.get(...)` in this way does NOT make a request - those can only be initiated on a client.  It registers the route handler so that in future whenever the server gets a matching HTTP request, it knows to call the function given here in the second parameter.

  * When that happens, two objects, request and response will be passed as parameters to our route handler. These represent 
    * the received HTTP request, which can be examined by the route handler (e.g. to find route or query parameters, or content in the request body), AND 
    * the HTTP response under construction (not yet sent), which our handler will generally fill in (perhaps including requested content in the body of the response) and set a status code on to indicate the outcome of the processing of the request.

You can read more in [Basic Routing](https://expressjs.com/en/starter/basic-routing.html) in the express starter docs.

# Basic C.R.U.D. operations (Create Read Update Delete)

## CREATING a resource

To allow the user to create a new instance of a resource, such as a recipe, we'd create the route handler to:

* match the `POST` HTTP method, and 
* use a route path of `/recipes`

```
app.post('/recipes', function (request, response) {

  const newRecipe = request.body
   //TODO:...
});
```

Note: the new content is normally submitted as part of the request body, and accessed with `request.body`.
However, before this is possible, see the following section `Accessing request.body in a POST request`.

## Accessing request.body in a POST request
If you are going to use the body of a POST request in a route handler, you will have to add one of two lines to first process the body.  How you do this depends on how the request has been submitted.  

### If the request has come from an HTML form:

if it has been submitted by HTML form you need to add the line
```app.use(express.urlencoded({ extended: false }))```

### If the request has come from `fetch` (e.g. in React), or from Postman

if it has come from a HTML form you need to add the line
```app.use(express.json())```

In both cases you can then say `request.body` to get either an object of key-value pairs, or the JSON which was posted.

[Official Express.js documentation about req.body](https://expressjs.com/en/api.html#req.body)

## READING a resource

To read *all* resources we make a route handler to match the `GET` HTTP method, and a route path of `/recipes`

To read *one* resource we make a route handler to match the `GET` HTTP method, and a route path of `/recipes/:id`, in order to match GET requests to real paths such as /recipe/117

## UPDATING a resource

To allow the user to update a resource, such as a recipe, we'd create the route handler to:

* match the `PUT` HTTP method, and 
* use a route path of `/recipes/:id`, to match an example of /recipes/117

```
app.put("/messages/:id", function (request, response) {
  const id = request.params.id;
  
  //TODO: find the recipe with the matching id
  

});
```

As with POST requests which create resources, we expect the changed content in the request body.
* This is accessed with `request.body`
* You must first use `app.use(express.json())` or `app.use(express.urlencoded({ extended: false }))` as discussed above in the section [Accessing request.body in a POST request]("#Accessing+request.body+in+a+POST+request)



## DELETING a resource

To allow the user to delete a resource such as a recipe, by id, we'd create the route handler to:

* match the `DELETE` HTTP method, and 
* use a route path of `/recipes/:id` to match an example of /recipes/117, as follows:

```
app.delete('/recipes/:id', function(req, res) {
  
  //look in the request params to get the id of the recipe to delete:
  const idToDelete = request.params.id;
  
  //TODO: delete the recipe with the matching id from your data source (e.g. in-memory array or mongoDB)
  //TODO: if the recipe was found and deleted successfully, return status 204 and an empty body.
});
```

Note that the request params will be strings, not numbers, so you may have to attempt to convert your id param to a number before trying to match it against recipe ids if those happen to be stored as numbers.


## Extracting values of "Query parameters"

* If you make a route with a path of `/quotes/search`
* ...and then you make a GET request for a URL like: http://localhost:3000/cars/search?color=blue&gears=5
* ...then you can obtain the query parameters from the request using: `request.query.color` and `request.query.gears`

[Official Express.js documentation about req.query](https://expressjs.com/en/api.html#req.query)

## Extracting values of "Route parameters"

* If you make a route with a path of `/quotes/:quoteId`
* ...and then you make a GET request for a URL like: http://localhost:3000/quotes/17
* ...then you can obtain the quoteId from the request using: `request.params.quoteId`

[Official Express.js documentation about Route Parameters](https://expressjs.com/en/guide/routing.html#route-parameters)


