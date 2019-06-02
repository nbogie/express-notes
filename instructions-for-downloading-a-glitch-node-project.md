# Downloading a glitch project and developing it locally

### On glitch website
* visit your desired glitch project's code page
* click on `tools` in the bottom left
* click on `git, import, and export` from the pop-up menu
* click on `read`
* click on `copy`
* this will copy the address of the git repo that glitch uses to store your project in

### in a terminal
* change directory into the parent directory that will contain your express project directory
* type `git clone ` but DO NOT press enter or return
* paste the git repo address from the clipboard, so that the full command looks SOMETHING like:
  `git clone https://api.glitch.com/git/YOUR-PROJECT-NAME`
* change directory into the newly created project directory
* run `npm install`
* run `PORT=3001 npm start`

### Test in a browser
* visit http://localhost:3001/
* change the path to test other routes
* test other non-GET routes with Postman
