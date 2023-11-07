# ![[Introduction to Express] - Build and Run 'server.js'](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to build the most basic structure of an **Express** server and know how to start it.

## Basic Structure of Express App

Here is a helpful outline of what a typical Express app does - let’s put this guide right in our **`server.js`**:

```js
// Here is where we import modules
// We begin by loading Express

import express from 'express'

// Here we create the Express app

const app = express()

// Configure the app (app.set)
// More to come...



// Mount Middleware (app.use)
// More to come...



// Here is where we will mount our routes



// Tell the app to listen on port 3000
// for HTTP requests from clients

app.listen(3000, function() {
  console.log('Listening on port 3000')
})
```

📚 The **`server.js`** file is typically the main entry point and configuration file for setting up an Express web server. It holds the middleware pipeline along with routes, and is where routing and server errors are handled.

😎 It's VERY normal to feel overwhelmed by **`server.js`**, and it will take you a few days to digest what is going on here. ***That is ok!***

## Nodemon

To run the app, we can easily use the `node` keyward followed by the name of the file you would like to run, in our case, `server.js`:

```bash
node server
```

> 📚 Note, when running node modules, you do not have to include the `.js` extension in the command.

Browsing to [`localhost:3000`](http://localhost:3000) will hit the app's root route.

However, any time changes are made to the application using this method, you'll have to stop and restart the server, ***every time!***

There is a better way... **NODEMON!**

![Nodemon Icon](./assets/nodemon-icon.png)

`nodemon` is a popular development tool used for automatically restarting our Express app when we save changes so no need to be continually restarting the server all the time!

You should have installed it during installfest; however, you can make sure you have the latest version by running:

```bash
npm i -g nodemon
```

> 🧠 We usually install command-line tools using the `-g` (global) option.

Thanks to the `main` key in `package.json`, we can start the server by simply running `nodemon`.

```bash
nodemon server
```

> ❗️ If we would run our server at this point we would receive an error since our app would be be trying to import a node module that we haven't installed yet. We'll run our server once the `express` module is installed.

> 😎 This will not change for the entire unit - we'll always run our server using `nodemon`.

You will see this all in action when you write your first route!
