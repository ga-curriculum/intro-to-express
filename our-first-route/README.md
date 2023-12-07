# ![Intro to Express - Our First Route](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to write routes for an **Express** server and understand the responsibilities of its path and callback.

## Hello World!

Let’s write the obligatory ***Hello, World*** application! We will be using the basic structure of our Express app we already set up.

## Our First Route

Let’s define a *route* in the proper section of our Express app:

```js
// Here is where we will mount our routes:

app.get('/', (req, res) => {
  res.send('<h1>Hello World!</h1>')
})
```

Like most web frameworks, Express uses the *HTTP Method* and the *Path* of the HTTP request to match a route defined in the application.

Above, we defined a route using the `get` method on the Express `app` object.

The `get` method defines a route that listens for a `GET` request. Other methods include `post`, `put`, and `delete` which map to the HTTP verbs of the same names.

The first argument provided to `app.get()`, `/`, defines the path for the route. In this case, the root of the application (the root of the application is just the hostname like [**`localhost:3000`**](http://localhost:3000)).

> In Express, all strings used to define a path should start with a forward-slash character (`/`).

The second argument provided to `app.get()` is a callback function.

Express will execute the route’s callback function only when a request comes in that matches the corresponding method and path for that route. 

The route’s callback function defines two parameters which we will name `req` & `res`. We could call them anything, but it's convention to use those names.

- `req`: Represents Express’s [**request object**](https://expressjs.com/en/5x/api.html#req)
- `res`: Represents Express’s [**response object**](https://expressjs.com/en/5x/api.html#res)

Express provides those two objects as arguments when it invokes the callback.

- The request (`req`) object has properties and methods to access information regarding the current HTTP ***request***, including any data the browser has sent.
- The response (`res`) object contains properties and methods used to send a response to the client. We've already done so using the `res.send()` method.

> 😎 Routes will always have a callback function with both `req` and `res` parameters. Be careful not to flip the `req` and `res` parameters when you are writing your callback function.

With all that out of thr way, use the URL bar of your web browser to go to [`localhost:3000`](http://localhost:3000). You should see something like this:

![Hello World Root](./assets/hello-world-root.png)

## Update the Route

Let's make a minor update to our root route, changing "Hello World!" to "Hello Express!":

```js
app.get('/', (req, res) => {
  res.send('<h1>Hello Express!</h1>')
})
```

Since we started our server using `nodemon`, the browser should reveal the update to our root route after we refresh the page!

![Hello World Root](./assets/hello-express-root.png)

## You Do: Define Another Route 💪

- Define another route that matches a `get` request to a path of `/home` that sends a response of `<h1>Home Page</h1>`.

- Test it by browsing to `localhost:3000/home`.