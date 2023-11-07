# ![[Introduction to Express] - Our First Route](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to write routes for an **Express** server and understand the responsibilities of it's path and callback.

# Express - Hello World!

Let’s write the obligatory ***Hello, World*** application!

We will be using the basic structure of our Express app we already set up.

## Our First Route

Let’s define a *route* in the proper section of our Express app:

```js
// Mount routes

app.get('/', (req, res) => {
  res.send('<h1>Hello World!</h1>')
})
```

> 📚 Note, using `.send()` is a general purpose way to respond to the request. It's kind of like using `console.log()`. ***Soon we'll be using more specific methods.***

Like most web frameworks, Express uses the *HTTP Method* and the *Path* of the HTTP request to match a route defined in the application.

In our first route, we defined a route using the `get` method on the Express `app` object.

The `get` method defines a route that listens for a `GET` request. Other methods include `post`, `put`, and `delete` which map to the HTTP verbs with the same names.

###  Run the Server

Let's start the server now by simply running `nodemon`:

```bash
nodemon server
```

And browse to [`localhost:3000`](http://localhost:3000) to hit the app's root route. You should see something like this:

![Hello World Root](./assets/hello-world-root.png)

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

> 😎 The most important takeaway here is that routes must always be mounted in **`server.js`**, even though code may be refactored differently in the future, and routes will always have a callback function with both `req` and `res` parameters. Also, be careful not to flip the `req` and `res` parameters when you are writing your callback function.

## Update the Route

Let's make a minor update to our root route:

```jsx
// Mount routes
app.get('/', (req, res) => {
  res.send('<h1>Hello Express!</h1>')
})
```

### Re-Run the app

Because we started our server using `nodemon`, after saving the changes to our file (`cmd-S`) and refreshing the page, the browser should reveal the update to our root route!

Browsing to [`localhost:3000`](http://localhost:3000) will hit our app’s root route that we defined and return: **Hello Express**.

![Hello World Root](./assets/hello-express-root.png)

Using your Dev Tools in the browser, we will find that despite just sending back the text of `<h1>Hello Express</h1>`, the browser put together a minimal HTML document to display it in. The send method is a general-purpose way to respond to the request; however, we’ll soon use more specific methods.

## You Do: Define Another Route (3 mins) 💪

- Define another route that matches a get request to a path of `/home` that sends a text response of `<h1>Home Page</h1>`.

- Test it by browsing to `localhost:3000/home`.

## Review Question ❓

Knowing what you know, do you think it's ok to define more than one route on the same path? For example:

```js
app.get('/cars', (req, res) => {
	res.send('Here is a list of my cars...')
})

app.post('/cars', (req, res) => {
	res.send('Thanks for the new car!')
})
```