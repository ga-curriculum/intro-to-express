# ![Intro to Express - URL Parameters](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to describe how parameters are used in URLs to access specific requested data.

## URL/Route Parameters

In our web apps, we often need to pass information, such as an identifier for a particular data resource, in the **path** of the HTTP request.

**URL Parameters**, also known as **Route Parameters**, work like parameters in functions, providing a way for data to pass into the route's callback function via the request URL.

Like JavaScript functions, where we define parameters in the function definition and pass arguments when the function is called, URL parameters act as placeholders in a route definition. When a request is made to that route, the actual values in the URL are treated as arguments.

![URL Parameters](./assets/url-parameters.png)

In Express, we define route parameters in the **path string** using a colon followed by the parameter name.

Here's an example:

```javascript
app.get('/:itemNumber', (req, res) => {
  // Prints: 123
  console.log(req.params.itemNumber);

  // Will send an H1 in the response with the content: Item 123
  res.send(`<h1>Item ${req.params.itemNumber}</h1>`);
});
```

In your browser, visit [`localhost:3000/123`](http://localhost:3000/123). Now visit [`localhost:3000/456`](http://localhost:3000/456). You should see the item number change from 123 to 456. Change the number to anything you want; the page should update accordingly upon refresh.

In the above route, the path `/:itemNumber` tells Express to create a route whose path is a `/` followed by any string (e.g., 123, 456, foo, bar, etc.). When a matching request comes in, Express will create a property on `req.params` with a key of `itemNumber` and a value of whatever comes after the slash in the request's path.

If the URL is [`localhost:3000/123`](http://localhost:3000/123), then `req.params.itemNumber` has the value 123. If the URL is [`localhost:3000/456`](http://localhost:3000/456), then `req.params.itemNumber` has the value 456.

## URL Parameters and Route Order

When defining routes with URL parameters, it's essential to consider the order in which the routes are defined. Consider the following two routes:

```js
app.get('/:name', (req, res) => {
  res.send(`Hello ${req.params.name}!`);
});

app.get('/about', (req, res) => {
  res.send('About Page');
});
```

We have two routes here:

- The first route has a path of `/:name` and will match any request that starts with a `/` followed by any string.
- The second route has a path of `/about` and will match any request that starts with `/about`.

Which route would match if we were to try to visit [`localhost:3000/about`](http://localhost:3000/about)? The first route would match because `/about` starts with a `/` followed by any string. This means the second route will never match because the first route will always match first.

So, when developing these routes, it's essential to consider the order in which they are defined. If we want the `/about` route to match, we must define it before the `/:name` route.

## 🎓 You Do: URL Parameters

Let's get in a rep of the above learnings:

- Create a new route that listens for a `GET` request to the path `/greet/:name`.
- When a request comes in, send a response that says "Hello, [name]!" where [name] is the value of the `name` parameter in the URL.
