# ![[tktk Module Name] - tktk Microlesson Name](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to tktk

# Ways to Respond to a Request

So far, we have responded in our route handler (callback) code by using the `res.send` method. The [**Express documentation for the Response object**](https://expressjs.com/en/4x/api.html#res) explains the other ways to respond to the HTTP request.

Here are the methods we’ll use the most:

- `res.render()` - Render a view template and send the resulting HTML to the browser.
- `res.redirect()` - Tell the browser to issue another GET request.
- `res.json()` - Send a JSON response (used when we communicate via AJAX).

<aside>
😎 We'll use these three methods when using the MEN stack and the MERN stack.

</aside>

## Rendering Views

Another of the three fundamental capabilities of a web framework is to use a view engine to render templates.

A template can include a mixture of static HTML and code that generates HTML dynamically. For example, code in a template could create a series of `<li>` elements for data provided by an array.

Express uses `res.render` to process a template using a *view engine* and return the resulting HTML to the browser.

Express can work with a multitude of *view engines*. [***EJS**](https://www.npmjs.com/package/ejs) (Embedded JavaScript)* is the view engine we are going to use in this course.

<aside>
📚 A *view engine* is a library that works in conjunction with a web app framework that handles the process of generating dynamic HTML content from templates and data. The view engine is responsible for rendering the final output (HTML code) to be sent to the client. *EJS (Embedded JavaScript)* is a type of view engine that can generate dynamic HTML content by embedding JavaScript code within HTML templates.

</aside>