# civicactions.com
CivicActions home site
=======

For an overview of the project structure please refer to the [Gatsby documentation - Building with Components](https://www.gatsbyjs.org/docs/building-with-components/).

## Requirements
* [Docker](https://docs.docker.com/install/)

Alternatively you can use a recent version of [Node.js](https://nodejs.org/en/) and [Yarn](https://yarnpkg.com/lang/en/) - however Docker is the preferred environment as it matches production.

## Install
Clone the git repository:
```sh
git clone git@github.com:CivicActions/civicactions.com.git
```

Go to the top level directory:
```sh
cd civicactions.com
```

Source an activate script. This will make CLI tools (running in Docker) available on your terminal and also download NPM dependencies.
```sh
. bin/activate
```

Fire up the development server:
```sh
gatsby develop
```
You should see the site by going to http://localhost:8000/  in your browser.
To turn off the server run `Ctrl + C`

You can also test a full build which will run with some additional compression steps and serve the site with the [Caddy](https://caddyserver.com/) web server, albeit without hot reloading.
```sh
fullbuild
```
You should see the site by going to http://localhost:8000/  in your browser.
To turn off the server run `Ctrl + C`

To force a rebuild you can just delete the sandbox and/or full images:
```sh
docker rmi -f home-sandbox home-full
```

To stop development and use your local versions of CLI tools run:
```sh
deactivate
```

## Development Workflow
To collaborate on this project first follow the install steps above to create a functional sandbox.

### Create your fork and add git remotes (one time)
 1. Fork this repo to your github account.
 2. In your CLI, add this main repo as a remote named origin 
``` 
git remote add origin git@github.com:CivicActions/civicactions.com.git
```
3. Add your fork as a remote named myfork (or any preferred name)
```
git remote add myfork [link used to clone your fork]
```

### Working in local branch

4. Create a new local branch with the naming convention `CA-xx(ticket number)-brief-ticket-title` and commit your changes to the ticket branch.
5. After working, run `git pull --rebase origin master` to pull in the latest changes.
6. Run `yarn install` to update the site with any new plugins.
7. Run `gatsby develop` to make sure the site builds as expected.
8. Push your changes to your fork `git push myfork`.
9. Create a PR in the main repo.

## Deploy

Pull requests are deployed automatically when merged.