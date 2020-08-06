# Node-Express-Deliverable

## Starting a Node app

```
npm init -y
```

## Node modules (how to make them, export them, and import them)

```
npm i express
npm i ets
npm i express-ejs-layouts
```

## Node packages (take note of any NPM packages you have used/researched)

* express
* ejs
* express-ejs-layouts

## Adding express to a node app

``` javascript
const express = require('express');

const app = express();

```

## Express routes

``` javascript
const express = require('express');
const router = express.Router();

router.get('/animals', function(req, res) {
    res.render('/faves/animals', {title: 'Favorite Animals', animals: ['sand crab', 'corny joke dog']})
  });
```

## Views

* Create views folder 'mkdir views'

``` javascript
app.set('view engine', 'ejs');
```
* now all the documents inside views require .ets instead of .js

## Templates

``` javascript
app.set('view engine', 'ejs');
app.use(ejsLayouts);
```

## Layouts

* npm install express-ejs-layouts
``` html
<!DOCTYPE html>
<html>
<head>
  <title>Faves&Hates</title>
</head>
<body>
  <%- body %>
</body>
</html>
```

* use layout
``` javascript
app.get('/', function(req, res) {
  res.render('home');
});
```

## Controllers

``` javascript
app.get('/foods', function(req, res) {
  res.render('faves/foods', {title: 'Favorite Foods', foods: ['coconut', 'avocado']});
});

app.get('/animals', function(req, res) {
  res.render('faves/animals', {title: 'Favorite Animals', animals: ['sand crab', 'corny joke dog']})
});
```
