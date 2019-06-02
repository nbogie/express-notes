# Code-Reading Exercise - Recipe API Server

* On your own you should have read this code for the recipe API, https://glitch.com/~cyf-recipes-reading-exercise?path=server.js
* With your neighbour decide answers for all of the following questions
* Note: Do NOT make requests to the server to test your answers, until you are told you may do so.

### In the route handler for `GET /recipes`
1. what status code will be returned if the server's list of recipes is empty?
2. what body content will be returned if the server's list of recipes is empty?

### In the route handler for `DELETE /recipes/:id`
3. what type of value does `recipes.findIndex` return?
4. what will `recipes.findIndex` return if it finds nothing?
5. What does this line do? ```recipes.splice(indexToDelete, 1)``` 

### In the route handler for `POST /recipes`
6. If a client submits a recipe object with unexpected properties, what will happen?
7. Will that recipe appear in the results if a client then requests `GET /recipes` ?

7.1. If SO, which properties will be missing?

7.2. If NOT, why not?

### In the route handler for `GET /recipes/search`
Your boss wants this route to return all of the recipe objects whose `title` property includes the text passed in as the query parameter `term`.  He wants only case-sensitive matches to be returned.

8. What is the bug in this route handler?  
9. How would you fix it?

### Miscellaneous questions

10. Considering *all* of the route handlers, which route handlers will NEVER make changes to the recipes data (the array `recipes`) on the server?
11. What is the first line of the function `updateRecipeInPlace` ?
12. In the only call to the function `app.put`, what is the type of the second parameter?
