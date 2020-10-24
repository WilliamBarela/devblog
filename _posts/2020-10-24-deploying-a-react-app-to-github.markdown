---
layout: post
title: "Deploying a React App to GitHub"
date: 2020-10-24 13:35
---

Deployment is a complex topic and one which requires skill, experience and funds to do.
Although one could deploy their frontend to a service such as Netlify, for small proofs of concept, a very nice alternative is to deploy to Github Pages.
Deploying a vanilla JS  website to Github Pages is a very simple task and best of all it is free.
However, when using a framwork like React with Redux, to optimize the deployed application one needs to build the project.

This presents a critical problem in that the output built application is completely different from your original code.
So, you have to publish your built application to a branch different than the one where you keep your source code.

A very nice solution which is available for this and that you you automate the process is a NPM package which you can save to your project as a dependency.
This package is called [https://www.npmjs.com/package/gh-pages](gh-pages). Once it is installed into your project and after a quick configuration of the package.json, you will be able to push the built project to the branch of your choice.

So, here is a quick guide on how to get started with gh-pages.
First, install it as a depdency in your project:

```bash
npm install gh-pages --save-dev
```

Then, once you have changed the setting in the Github Repo to allow Github pages and you have chosen the branch to serve from, you should checkout a different branch. That is, if you are in **main**, you should run ```git checkout -b source-code``` or whatever branch name you would like to use so you do not overwrite your curent code.
Next, modify the _package.json_ file to incorporate new scripts to help you build your project:

```javascript
"predeploy": "npm run build",
"deploy": "gh-pages -b main -d build"
```

This provide you with two new npm scripts that will help you with the deploy. But it is even simpler for you because you only need to run the following to deploy:

```bash
npm run deploy
```

Gh-pages will run the predeploy and then upon a success push to the main branch said build. And that, is as simple as it is to deploy a fully functional React (even React Redux) web application.

One key thing to note is that gh-pages caches the built project (without touching your source code branch, however when you deploy it pushes that built site to your master/main branch by default (or the one you specify in the packages.json); however, it will not update that branch on your computer, so you will need to pull the changes once it is deployed if you are interested in the build.
