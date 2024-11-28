<h1>
  <span class="headline">Intro to Express</span>
  <span class="subhead">Building Our First Route</span>
</h1>

**Learning Objective:** Students will learn to write and understand routes in an Express server, focusing on the path and callback function.

## Introduction to Express routing: "Hello World!"

In programming tradition, the first step in learning a new language or framework is writing a "Hello, World!" program. Let's create our first Express route to display "Hello, World!" in the browser using the Express app structure we've already set up.

### Writing our first route

In Express, *routes* handle incoming requests to the server based on the HTTP method and request path. We'll start with a simple `GET` route:

```js
// Define routes here:

app.get('/', (req, res) => {
  res.send('<h1>Hello World!</h1>');
});
```

> 📚 A *route* in web development is a specified path or endpoint in a web application that determines how an application responds to client requests to a particular URL pattern.

> Other Express methods include `post`, `put`, and `delete`, which map to the HTTP verbs of the same names.

Let's review the route components:

- **HTTP Method**: We use the Express `app.get()` method, corresponding to the HTTP `GET` request.
- **Path Argument**: The first argument `'/'` signifies the root path (`localhost:3000` on your local server).
- **Callback Function**: The second argument is a callback function that Express calls when the route is matched. It takes two parameters:

  - `req`: The [**Request Object**](https://expressjs.com/en/5x/api.html#req), providing request details.
  - `res`: The [**Response Object**](https://expressjs.com/en/5x/api.html#res), used to send a response back to the client.
  
>  Routes will always have a callback function with both `req` and `res` parameters. When writing your callback function, be careful not to flip the `req` and `res` parameters.

> In Express, all strings that define a path should start with a forward-slash character `'/'`.

### Testing the route

Check your terminal to ensure your server is still running, if not restart it with:

```bash
nodemon
```

Visit [`localhost:3000`](http://localhost:3000) in your browser. You should see "Hello World!" displayed:

![Hello World Root](./assets/hello-world-root.png)

Seeing your first "Hello World" is a huge accomplishment. Congrats!  🎉

### Updating our route

Let's modify our route to respond with "Hello Express!" instead:

```js
app.get('/', (req, res) => {
  res.send('<h1>Hello Express!</h1>');
});
```

With `nodemon` running, the server automatically updates. Refresh your browser to see the new message:

![Hello Express Root](./assets/hello-express-root.png)

## 🎓 You Do

### Create a New Route

Now it's your turn:

- Define a route for the path `/home` that sends back `<h1>Home Page</h1>`.
- Test your new route by navigating to `localhost:3000/home` in your browser.
- What do you see?
