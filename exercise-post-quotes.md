# In-class exercise: Allow adding of new quotes via POST

1. remix the starting project
1. change the `server.js` to add the line: 

```app.use(express.urlencoded({ extended: false }))```

Add a route which will handle POST requests to `/quotes`

Do something with the body of the HTTP request (request.body)

//1. Return it in the response, to show you're receiving it.
//1. Test by requesting '/' and using the form there which will post a quote
//1. Change your code to add the request body to your list of quotes
//1. Test it again, this time afterwards look at `/quotes` to see if they're been added/


