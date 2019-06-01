# Downloading a glitch project and developing it locally

### On glitch website
* visit your desired glitch project's code page
* click on `tools` in the bottom left
* click on `git, import, and export` from the pop-up menu
* click on `download project`

### On your computer
* find the downloaded zip (.tgz) file on your computer
* right-click on it, and choose `extract to...`
* choose a destination for the project - e.g. next to any other Node projects
* find the new directory and rename it to remove the timestamp

### in a terminal
* `cd` into the directory containing `package.json`
* run `npm install`
* run `PORT=3001 npm start`

### Test in a browser
* visit http://localhost:3002/
* change the path to test other routes
* test other non-GET routes with Postman
