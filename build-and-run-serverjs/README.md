# ![[Introduction to Express] - Build and Run 'server.js'](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to tktk

## Basic Structure of Express App

Here is a helpful outline of what a typical Express app does - let’s put this guide right in our **`*server.js*`**:

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

📚 The ***`server.js`*** file is typically the main entry point and configuration file for setting up an Express web server. It holds the middleware pipeline along with routes, and is where routing and server errors are handled.

😎 It's VERY normal to feel overwhelmed by `server.js`, and it will take you a few days to digest what is going on here. ***That is ok!***

Run the app:

node server
Browsing to localhost:3000 will hit our app's root route that we defined and return "Hello World!".

Using DevTools, we will find that despite just sending back the text of
<h1>Hello World!</h1>,
the browser "built" a minimal HTML document to display it in.

Using send() is a general purpose way to respond to the request, however, it's kind of like using console.log() - soon we'll be using more specific methods.

# Nodemon

`nodemon` is a popular development tool used for automatically restarting our Express app when we save changes - no more restarting the server all the time!

You should have installed it during installfest; however, you can make sure you have the latest version by running:

```bash
npm i -g nodemon
```

<aside>
🧠 We usually install command-line tools using the `-g` (global) option.

</aside>

Thanks to the `main` key in **`package.json`**, we can start the server by simply running `nodemon`.

<aside>
😎 This will not change for the entire unit - we'll always run our server using `nodemon`.

</aside>

Back to routing!