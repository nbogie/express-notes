Exercise: simulate HTTP messages and route handlers

In groups, work out the detail of the HTTP messages and route handlers needed to deal with the following stories.  
(In all cases assume the recipe API lives at https://api.cyfrecipes.site)

## 1. I want to read ALL recipes
## 2. I want to read this ONE recipe.  Its `id` is 17 and its `title` is "Lasagne".
## 3. I want to create this new recipe:

```
{
  "title": "Adana",
  "ingredients": [
    "1 kg ground lamb",
    "Kosher salt",
    "4 teaspoons ground cumin, divided",
    "4 tablespoons ground sumac, divided",
    "4 tablespoon ground Urfa pepper flakes, divided",
    "4 tablespoons ice-cold water"
  ],
  "prepTime": 60,
  "steps": [
    "For the Kebabs: Combine...",
    "Meanwhile,...",
    "Serve kebabs with warm bread..."
  ],
  "author": "Mohammad",
  "countryOfOrigin": "Turkey",
  "course": "Main"
}
```

## 4. I want to delete the following recipe
```
{
  "id": 31,
  "title": "Adana",
  "ingredients": [
    "1 kg ground lamb",
    "Kosher salt",
    "4 teaspoons ground cumin, divided",
    "4 tablespoons ground sumac, divided",
    "4 tablespoon ground Urfa pepper flakes, divided",
    "4 tablespoons ice-cold water"
  ],
  "prepTime": 60,
  "steps": [
    "For the Kebabs: Combine...",
    "Meanwhile,...",
    "Serve kebabs with warm bread..."
  ],
  "author": "Mohammad",
  "countryOfOrigin": "Turkey",
  "course": "Main"
}
```
