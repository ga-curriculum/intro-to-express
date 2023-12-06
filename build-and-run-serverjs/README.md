# ![[Introduction to Express] - Build and Run 'server.js'](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to build the basic structure of an **Express** server and know how to start it.

## Install the Express Module

Before we begin building our server, we'll need to install the Express module in this project:

```bash
npm i express
```

> 📚 Note that `i` is an alias for `install`.

Now the Express framework is available to use when building our application. Without this step, if we were to try to run our server code, we would receive an error since our app would be be trying to import code from a node module that we haven't installed yet.

Now that `express` is installed, let's write the basic code needed to create our server.

## Basic Structure of Express App

Here is an outline of what a typical Express app does - let’s put this guide right in our **`server.js`** file:

```js
// Here is where we import modules.
// We begin by loading Express:

const express = require('express')

// The "express" variable we just created has a lot of different functionality that helps developers build web applications. We could have called it anything, but let's stick to something meaningful.
// Below we use express() to generate an "app" object and assign it to a variable. The "app" object has methods on it that handle things like creating routes and having the server start listening for requests.

const app = express()

// Here is where we will mount our routes (left intentionally empty, for now):




// Tell the app to listen on port 3000 for requests from clients.
// Every computer has thousands of ports on which it can listen for requests, but each port can only be assigned to one software application at a time. Once assigned, requests can come in to that port and be handled by the application, much like a boat sails into an actual port in real life.

app.listen(3000, () => {
  console.log('Listening on port 3000')
})
```

📚 The **`server.js`** file is typically the main entry point and configuration file for setting up an Express web server.

## Nodemon

To run the app, we could use the `node` keyword followed by the name of the file you would like to run (in our case, `server.js`):

```bash
node server.js
```

However, any time changes are made to the application's code using this method, you'ld have to stop and restart the server, ***every time!***

There is a better way... **NODEMON!**

![Nodemon Icon](./assets/nodemon-icon.png)

`nodemon` is a popular command line tool used for automatically restarting our Express app when we save changes to its code. No more need to continually restart the server all the time!

Install it using:

```bash
sudo npm i -g nodemon
```

> 🧠 We usually install command-line tools using the `-g` (global) option. `sudo` may or may not be necessary depending on your computer.

Thanks to the `main` property in `package.json`, we can start the server by simply running `nodemon`, and it will automatically run `server.js`.

## Run the Server

Now that we have `nodemon` installed, let test out both that tool and our code by running our server. Run the following command: 

```bash
nodemon
```

Our server should be up and running, and you should see something like this:

![Server Running](./assets/server-running.png)
