# ![[Introduction to Express] - Our First Route](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to tktk

# Express - Hello World!

Let’s write the obligatory ***Hello, World*** application!

We will be using the basic structure of our Express app we already set up.

### Install the Express Module

Let's use `npm` to install the Express module in this project:

```bash
npm i express
```

> 📚 Note that `i` is a shortcut for `install`.

Without this step, if we would try and run our server at this point we would receive an error since our app would be be trying to import a node module that we haven't installed yet.

## Our First Route

Let’s define a *route* in the proper section of our Express app:

```js
// Mount routes

app.get('/', function(req, res) {
  res.send('<h1>Hello, World</h1>')
})
```

> 📚 Note, using `.send()` is a general purpose way to respond to the request. It's kind of like using `console.log()`. ***Soon we'll be using more specific methods.***

Like most web frameworks, Express uses the *HTTP Method* and the *Path* of the HTTP request to match a route defined in the application.

In our first route, we defined a route using the `get` method on the Express `app` object.

The `get` method defines a route that listens for a `GET` request. Other methods include `post`, `put`, and `delete` which map to the HTTP verbs with the same names.

## The Route's Path

The first argument provided to `app.get()`, `/`, defines the path for the route. In this case, the root of the application (the root of the application is just the hostname like [**`localhost:3000`**](http://localhost:3000))

> **In Express, all strings used to define a path should start with a forward-slash character (`/`).** 

## The Route’s Callback

The second argument provided to `app.get()` is a callback function:

Express will execute the route’s callback function only when a matching HTTP request (HTTP Method + Path) is received.

The route’s callback function defines two parameters which we will name: `req` & `res`

- `req`: Represents Express’s [**request object**](https://expressjs.com/en/4x/api.html#req)
- `res`: Represents Express’s [**response object**](https://expressjs.com/en/4x/api.html#res)

Express provides those two objects as arguments when it invokes the callback.

- The request (`req`) object has properties and methods to access information regarding the current HTTP ***request***, including any data the browser has sent.
- The response (`res`) object contains properties and methods used to ***end the request/response cycle***. We've already done so using the `res.send()` method.

> ❓ What is a request? What is a response? What is the request response cycle?

> 😎 We'll refactor some of this code soon, but the most important takeaway is that routes must always be mounted in **`server.js`**, and routes will always have a callback function with both `req` and `res` parameters. Also, be careful not to flip the `req` and `res` parameters when you are writing your callback function.

###  Run the Server

Let's start the server now by simply running `nodemon`.

```bash
nodemon server
```

## Update the Route

Let's make a minor update to our root route:

```jsx
// Mount routes
app.get('/', function(req, res) {
  res.send('<h1>Hello Express</h1>')
})
```

Refreshing the page will reveal that it didn’t work! This happens because we have to restart the server after every change. Go ahead and ...

## Re-Run the app

End the currently running command in the terminal with `**Ctrl + C`** and restart it with:

```bash
node server
```

Browsing to [`**localhost:3000**`](http://localhost:3000) will hit our app’s root route that we defined and return ***hello, friend***.

Using your Dev Tools in the browser, we will find that despite just sending back the text of `<h1>Hello Express</h1>`, the browser put together a minimal HTML document to display it in. The send method is a general-purpose way to respond to the request; however, we’ll soon use more specific methods.

To get around having to restart the server after every change we make, we can use a fun command-line tool called...


You Do: Define Another Route (3 mins) 💪
Define another route that matches a get request to a path of /home that sends a text response of <h1>Home Page</h1>.
Test it by browsing to localhost:3000/home.
Review Question ❓
Knowing what you know, do you think it's ok to define more than one route on the same path? For example:
app.get('/cars', function(req, res) {
	res.send('Here is a list of my cars...')
})

app.post('/cars', function(req, res) {
	res.send('Thanks for the new car!')
})