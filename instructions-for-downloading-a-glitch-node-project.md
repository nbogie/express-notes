# Downloading a glitch project and developing it locally

### 1. On glitch website, get the glitch git repo address
* visit your desired glitch project's code page
* click on `tools` in the bottom left
* click on `git, import, and export` from the pop-up menu
* click on `read`
* click on `copy`
* this will copy the address of the git repo that glitch uses to store your project in

### 2. In a terminal, clone the repo to your local machine
* change directory into the parent directory that will contain your express project directory
* type `git clone ` but DO NOT press enter or return
* paste the git repo address from the clipboard, so that the full command looks SOMETHING like:
  `git clone https://api.glitch.com/git/YOUR-PROJECT-NAME`

### 3. In a terminal install and start
* change directory into the newly created project directory
* run `npm install`
* run `PORT=3001 npm start`

### 4. Test in a browser
* visit http://localhost:3001/
* change the path to test other routes
* test other non-GET routes with Postman

### You're done!

All done!  the next bit is just if you want to store your work on github.


### 5. Optional: Store in a new repo on GitHub

* Open github.com in a browser (ensure you are logged in)
* In the top-right click the plus (+) sign
* Choose "new repository"
* Add a suitable name for the repository. e.g. `chat-API`
* Don't change anything else
* Click `create repository` at the bottom of the form
* Find the section entitled "...or push an existing repository from the command line"
* Copy the FULL `git remote add origin` command from that section
* Paste it into terminal but change `origin` to `github` and ensure it runs with no errors
* Run: `git push -u github master`
* Reload your github page and explore to ensure your most recent code is there.
* All done!  Note that your local repo now has two remotes: `github` (points to your repo on github) and `origin` (points to your repo on glitch).
