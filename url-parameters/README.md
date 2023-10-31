# ![[tktk Module Name] - tktk Microlesson Name](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to tktk

URL/Route Parameters
In our web apps, we will often need to pass information, such as an identifier for a certain data resource, in the path of the HTTP request.
URL Parameters, also known as Route Parameters, just like parameters in functions, provide a way for data to pass into the router & controller via the URL of the request.
In Express, we define route parameters in the path string using a colon, followed by the parameter name.
To implement show functionality, so that we can view individual todos we need to utilize req.params.
Express’s req.params object will have a property for each route parameter defined. For example, a route defined like this:
router.get('/category/:catName/', ...)

and a link like this:

```html
<a href="/category/socks">Socks!</a>
```

would have a `req.params` available in the controller of:

```jsx
console.log(req.params.catName) //=> "socks"
```

Note that all route param values are strings.

<aside>
😎 Your understanding of this concept is vital to your success this unit, but you likely won't grasp it immediately - this is something that comes with repetition and you're going to get a lot of it this unit.

</aside>