---
layout: post
title: "Creating a React Redux Web Application"
date: 2020-09-17 15:55
---

Web development has grown at an astounding pace and today there are many alternative paradigms to choose from when making a frontend web application.
Back in the day, when Javascript, HTML and CSS were enough, package dependancies were not a worry on any frontend dev's mind. Nevertheless, the shift has been to move to modes of composing web applications which make them easier to understand and maintain over the life of the application.
Of all of the frontend libraries and frameworks to choose from, React.js, Angular.js and Vue.js are the most widely used. So, I just wanted to write a blog post which shows exactly how one would set up such an application and highlight some packages which can make one's development life easier.

Just as a quick overview, here are the main technologies I will be writing about:

- React
- Redux
- React-Router
- Redux Thunk

## React/Redux

### Motivation
Why not just use plain Javascript, HTML and CSS? React helps you to build components with ease and can then be used by other components to compose a whole web application or just portions of it.
Futhermore, JSX, Javascript XML, is a markup language which  which you can use with React to help yourself to abstract away Javascript's .createElement() and .appendChild() methods to get a crystal clear view of a component's HTML structure.
Although React comes with the ability to manage state within your application, it requires that you keep your state in the uppermost parent of the hierarchy a tree of components that need it and pass it down. Many times this forces you to violate Seperation of Concerns by requiring you to keep state in a component that is the not the logical owner of that data. In a larger application, this can be a nightmear of state management.
This is where Redux comes in. Redux, although again an option in a sea of options, helps you to abstract state management away from the React components and allows you to set up a data Store which contains the entirety of state in the application at a given time. Like all additional libraries, it creates its own headaches and by the admission of Redux's own website it is not always necessary.

### How to Set Up a React Redux application:

``` bash
npx create-react-app my-app-name --template redux
```

### Adding Redux to a Pre-Existing React App
```bash
# install redux core
npm install redux

# to also get redux-thunk, run this instead:
# npm install @reduxjs/toolkit

# install complementary packages
npm install react-redux
npm install --save-dev redux-devtools
```

## React-Router
Single page applications are cool (not always necessary, and also more demanding and difficult to make and maintain). Not being able to bookmark a page on a SPA -- not cool at all. Telling your users to not use the "Back" button -- insanely not cool.
To give your users the ability to use basic functions of a web browser and navegate to a page of interest in the future means that we either need to use the Javascript History API and build things ourselves (painful) or we can choose to not reintent the wheel and just use React-Router which comes in a web and native versions.
Yes, it sucks to have to learn the DSL of yet another package to handle our routing and history; however, would you want to tackle the alternative of making your own, quite posibility buggy, system?

### How to install React Router DOM (web applications only)

```bash
npm install react-router-dom
```

### Basic Route Creation
```bash
// Agave.js or any other file where you need to use the Router
import React from 'react'
import {
  BroswerRouter as Router,
  Route,
  Switch,
} from 'react-router-dom';

import AgaveIndex form '../views/agave/Index.js;
import AgaveNew from '../views/agave/New.js';

export default function Agave () {
  return (
    <Router>
      <Switch>
        <Route path="/agave">
          <AgaveIndex />
        </Route>
        <Route path="/agave/new">
          <AgaveNew />
        </Route>
      </Switch>
    </Router>
  )
}
```

The useRouteMatch() and useParams() functions and the Link component are also very useful for keeping your routes and links DRY.
These are definitely worth it to look through the documentation. It is important to keep in mind too that there is no default export in React Router, so you have to use { } when importing for any of the components or functions


## Redux Thunk
A Redux store only allows you to synchronous updates by dispatching an action. For a web application which is pulling its data from an API, we needs a middleware to help extend the abilities of Redux so that we can get data asynchronously.
That is where Redux Thunk comes in. Who'd a thunk it?

### How to install Redux Thunk

```bash
npm install redux-thunk
```

### Configuration

```javascript
// App.js
import ReduxThunk from 'redux-thunk';
```

## Conclusion
In a future post, I will go into further detail of how to connect a React App to a Redux store. Stay tuned.
