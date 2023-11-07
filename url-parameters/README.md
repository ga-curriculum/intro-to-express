# ![[Introduction to Express] - URL Parameters](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to describe how parameters are used in URLs to access specific requested data.

### URL/Route Parameters

In our web apps, we will often need to pass information, such as an identifier ***(often times an id)*** for a certain data resource, in the **path** of the HTTP request.

**URL Parameters**, also known as **Route Parameters**, just like parameters in functions, provide a way for data to pass into the router & controller via the URL of the request.

In Express, we define **route parameters** in the **path string** using a **colon**, followed by the **parameter name**.

Let's take a look at this analogy where we are working with a ***data entity*** called **Todos**, and see how parameters perform the same action in functions and routes, but just differ in syntax...

![Params Analogy](./assets/params-analogy.png)

^ **[tktk tktk This is not the perfect asset but I think the analogy is extremely helpful for visual learners.]**

To implement **show** functionality, so that we can view ***individual*** todos we need to utilize `req.params`.

Express’s `req.params` object will have a property for each route parameter defined. For example, a route defined like this accessing a **Cats** data entity:

```bash
router.get('/cats/:catName/', ...)
```

and a link like this:

```html
<a href="/cats/socks">Socks!</a>
```

would have a `req.params` available in the controller of:

```js
console.log(req.params.catName) //=> "socks"
```

> 📚 Note that all route params values are strings.

This works perfectly in the case above where we are utilizing the cat's name, `"socks"`. You will probably be looking to match that params value to the particular cat in the data entity, which probably has a `name` attribute with a value of `"socks"` (a string). In this case:

```js
req.params.catName === Cat.name //=> true
```

Both values and types match. However, in the case of the Todos data entity in the example above, the `2` being entered would actually be the string of "2" in `req.params`, not the number `2`. So in this case:

```js
req.params.id === Todos.id //=> false
```

The values are the same, `"2"` and `2`, but their types are not. Be sure to convert strings to the correct data type that is stored in the data entity.

> 😎 Your understanding of this concept is vital to your success this unit, but you likely won't grasp it immediately - this is something that comes with repetition and you're going to get a lot of it this unit.
