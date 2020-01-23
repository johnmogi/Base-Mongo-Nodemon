[full mongo, nodemon course here](https://www.youtube.com/watch?v=qj2oDkvc4dQ&list=PLZlA0Gpn_vH8jbFkBjOuFjhxANC63OmXM&index=5)

0. update everything:
Visual Studio
npm - npm install -g npm@latest

1. new folder
2. npm init -y
3. change index.js in package to server.js
4. npm i express ejs express-ejs-layouts
5. npm i --save-dev nodemon
6. package.json - 
replace test with - 

 "start": "node server.js", 
 "devStart" :  "nodemon server.js"

 7. create server.js:
const express = require('express')
const app = express()
const expressLayouts = require('express-ejs-layouts')

const indexRouter = require('./routes/index')
app.set('view engine', 'ejs')
app.set('views', __dirname + '/views')
app.set('layout', 'layout/layout')
app.use(expressLayouts)
app.use(express.static('public'))

app.use('/', indexRouter)
app.listen(process.env.PORT || 3000)

8. npm run devStart

9. create the following folders at root:
views
public
models
routes

10. create index.js at routes folder:
const express = require('express');
const router = express.Router()

router.get('/', (req,res) =>{
    res.send('Hello world')
})

module.exports= router

11. hit http://localhost:3000/ on browser- "hello world"