# Exercise: Allow adding of new quotes via POST (5-15 minutes)

## Objective
Change a quote API server to allow POSTs of new quotes.

The new quotes should be added to your quotes list, which is just an array in memory.

You can assume the POSTed quotes are all in the correct JSON format.

The route should be `/quotes` and the HTTP method should be POST.

## What should I start with?
You should use [OUR starting project: cyf-quotes-post-start](https://glitch.com/~cyf-quotes-post-start), NOT your own existing quote server.  This is because our project has an HTML form for creating new quotes.

When you remix our starting project, immediately rename it as `cyf-mussie-quotes-v2` but change it for YOUR name.

Then you can visit `/` and submit the form there, when you are ready to try to submit new quotes!

## Getting help

* You should refer to the [official Express documentation on req.body](https://expressjs.com/en/api.html#req.body) to help you with this.
* Or you can refer to [this small express cheatsheet](express-cheatsheet.md)

##  My quotes keep being lost
* Your node/express program on glitch is automatically reloaded each time you make a change.  This reloading will mean your array of quotes is initialised again.  When you are ready to test, don't edit the project at all!

## When you are finished
* When you are finished (including testing), DM your URL via Slack to someone sitting next to you and they must test if your API works!
