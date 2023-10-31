# ![[tktk Module Name] - tktk Microlesson Name](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to tktk

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