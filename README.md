# How to deploy React App to GitHub Pages

Do you have a static react app and want to deploy that, then well you are in the right place all you need for your deployment is a git account. Keep reading at the end of this you might end up knowing one more reason to fall in love with git. let’s get started

# Pre-requisites:

All you need to do this is a GitHub account also a machine Installed with Git (Set up Git).
As we are deploying a react application It’s good to make sure Node.js and Npm are installed well.
You’ll need to have Node 8.10.0 or later on your local machine.

# Step-1.Creating a simple application

First, lets create a simple react application my-app using create-react-app.

#install create-react-app
$ npm install -g create-react-app
#creating a new react app from the bootstrap
$ create-react-app my-app

navigate to the newly created directory “my-app” and run the application to see its working fine without any error.
It might take a while once that is completed, install GitHub Pages package as a dev-dependency.Github Pages is a platform to create beautiful static websites for the repositories, using the code present in the respected repository. We can also manually create GitHub Pages for any repository by going through the documentation here. But for this post, I am going to use ‘gh-pages’ package which will automatically achieve this goal for me.

#navigate to the app folder
$ cd my-app
#install github pages as dev dependency
$ npm install gh-pages --save-dev

# Step-2.Adding properties to Package.json

The first property we need to add is the homepage, we will define this as a string and the value will be
“http://{username}.github.io/{repo-name}”

{username} is your GitHub username, and {repo-name} is the name of the GitHub repository you created it will look like this
Secondly in the existing scripts property we to need to add predeploy and deploy.

“scripts”: {

“predeploy”: “npm run build”,

“deploy”: “gh-pages -d build”

}

at the end of this package.json looks like this
<br/>

<div style="text-align: center;">
    <img src="https://res.cloudinary.com/dbbyhhnom/image/upload/v1698132164/package_Json_yvrd5t.png" style="max-width:70%;box-shadow:0 2.8px 2.2px rgba(0, 0, 0, 0.12)">
</div>
<br/>

# Step-3.Creating git repository:

create a new repository under your git hub account.make sure the repository name in the github matches the one in you homepage in your package.json file.
the repository name in the github should match the one in you homepage in your package.json file.
<br/>

<div style="text-align: center;">
    <img src="https://res.cloudinary.com/dbbyhhnom/image/upload/v1698132164/Repository_l7p5bd.png" style="max-width:70%;box-shadow:0 2.8px 2.2px rgba(0, 0, 0, 0.12)">
</div>
<br/>

and the next step is to convert the local react project to a git repository.

#create a new git repository
$ git init
#add all changed file paths to staged changes
$ git add .
#commit all staged changes
$ git commit -m 'initial commit'
#add remote repository
$ git remote add origin {get the URL of the repo}
#pushed local repository to remote repository on GitHub
$ git push origin master

# Step-4.Deployment:

So far good, and now its time for deployment using the following command

#build application\
$ npm run build
<br/>

<div style="text-align: center;">
    <img src="https://res.cloudinary.com/dbbyhhnom/image/upload/v1698132164/npm_run_build_scpslp.png" style="max-width:70%;box-shadow:0 2.8px 2.2px rgba(0, 0, 0, 0.12)">
</div>
<br/>

#deploy application\
$ npm run deploy
<br/>

<div style="text-align: center;">
    <img src="https://res.cloudinary.com/dbbyhhnom/image/upload/v1698132164/npm_run_deploy_wacqhs.png" style="max-width:70%;box-shadow:0 2.8px 2.2px rgba(0, 0, 0, 0.12)">
</div>
<br/>
