# ![[Introduction to Express] - Setup](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to generate and initialize a new `node` project with the intention of creating an **Express** server.

Open your Terminal application and navigate to your `~/code/ga/lectures` directory:
```bash
cd ~/code/ga/lectures
```

Make a new directory called `express-intro`, then enter this directory:

```bash
mkdir express-intro
cd express-intro
```

Create a `node` project along with its `package.json` file by using this command:

```bash
npm init
```

During initialization, you will be prompted to customize your project and the `package.json` file.

At this point, accept the defaults (by simply just hitting `return/enter` for each prompt without adding any values), ***except for the entry point*** - set this to be `server.js`.

Add a file to our directory called `server.js`:

```bash
touch server.js
```

Open the project's folder in your code editor:

```bash
code .
```
