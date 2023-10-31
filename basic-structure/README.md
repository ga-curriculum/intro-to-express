# ![[tktk Module Name] - tktk Microlesson Name](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to tktk

# Express - Hello World!

Let’s write the obligatory ***Hello, World*** application:

## Basic Structure of Express App

Here is a helpful outline of what a typical Express app does - let’s put this guide right in our **`*server.js*`**:

// import modules

import express from 'express'

// create Express app

const app = express()

// configure the app (app.set)



// mount Middleware (app.use)



// mount routes



// tell the app to listen on port 3000

app.listen(3000, function() {
  console.log('Listening on port 3000')
})

<aside>
📚 The ***`server.js`*** file is typically the main entry point and configuration file for setting up an Express web server. It holds the middleware pipeline along with routes, and is where routing and server errors are handled.

</aside>

<aside>
😎 We'll always use `**server.js`,** but we won't write it from scratch like we are today. It's VERY normal to feel overwhelmed by `**server.js**`, and it will take you a few days to digest what is going on here. ***That is ok!***

</aside>