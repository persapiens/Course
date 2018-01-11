# Pipeline Basics

In this workshop, we'll cover the basics of setting up a barebone pipeline, consisting of hooks.

## Hooks

#### A simple hook

Create a local git repository (using `git init`) in a new directory. Create a "post-commit" file in `.git/hooks/`. Inside the file, create a command that will open a web page immediately after a commit is performed to that repo.

Some hints: 
* http://stackoverflow.com/questions/8967902/why-do-you-need-to-put-bin-bash-at-the-beginning-of-a-script-file
* `chmod`
* `start` for windows, `open` for mac/linux

## A Simple Pipeline

Clone the [app repo](https://github.com/CSC-DevOps/App).

### Initializing our endpoints.

We'll create an endpoints for our deployment, a "production" endpoint for our.    [See guide](http://toroid.org/ams/git-website-howto) for more details.

Inside the App directory, create a directory structure as follows:

* deploy/
  * production.git/
  * production-www/

To ensure we have a git repo that will always have files that reflect the most current state of the repo, we will use a "bare" repository, which will not have a working tree.  Using a hook script, the changes will then be checked out to public directory.

    cd deploy/production.git
    git init --bare

##### Post-Receive Hook

At `production.git/hooks/` place a `post-receive` file, with the following content:

    GIT_WORK_TREE=deploy/production-www/ git checkout -f
    echo "Pushed to production"

**Hints**

* You must create the production-www folder manually.
* You may have to add executable permissions using in *nix systems `chmod +x post-receive`.
* **Ensure that there is a script header**, such as `#!/bin/sh`, on the first line.
* Set an absolute path for the GIT_WORK_TREE.
* It will not work the first time.

### Creating a remote

Deploying Commits and Copying Bits

    git remote add prod file://deploy/production.git

You can now push changes in the following manner.

    git push prod master

You may have to create a simple commit before pushing.


### Running deployed app.

You should be able to run and view app at localhost:9000/ 
    
    cd deploy/production-www
    npm install
    node main.js 9000

### Thinking about pipelines

What else could you use hooks for? What might you want to do before pushing changes to production?


