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

## Extracting values of query parameters

* If you make a route with a path of `/quotes/search`
* ...and then you make a GET request for a URL like: http://localhost:3000/cars/search?color=blue&gears=5
* ...then you can obtain the query parameters from the request using: `request.query.color` and `request.query.gears`

[Official Express.js documentation about req.query](https://expressjs.com/en/api.html#req.query)

## Extracting values of "Route parameters"

* If you make a route with a path of `/quotes/:quoteId`
* ...and then you make a GET request for a URL like: http://localhost:3000/quotes/17
* ...then you can obtain the quoteId from the request using: `request.params.quoteId`

[Official Express.js documentation about Route Parameters](https://expressjs.com/en/guide/routing.html#route-parameters)

## Accessing request.body in a POST request
If you are going to use the body of a POST request in a route, you will have to add one of two lines to first process the body.  If the request has come from
### ...from an HTML form:

if it has come from a HTML form you need to add the line
```app.use(express.urlencoded({ extended: false }))```

### ...from fetch (e.g. in React), or from Postman
if it has come from a HTML form you need to add the line
```app.use(express.json())```

In both cases you can then say `request.body` to get either an object of key-value pairs, or the JSON which was posted.

[Official Express.js documentation about req.body](https://expressjs.com/en/api.html#req.body)
