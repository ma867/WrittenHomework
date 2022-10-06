# RESTful Routes
## Index 
The Index route allows the client to see all the elements in our database. Example: if you have a database of fruits, the index route will display all the elements.
Uses the GET method.
  ```
  //Use a GET request on endpoint /fruits
    app.get('/fruits', (req, res) => {
    //Using Mongoose's method, find, retrieve all the fruits from the fruits database
    Fruit.find({}, (err, foundFruits) => {
      //If there is an error retrieving the fruits, log it
      if(err){
        console.error(err)
        res.status(400).send(err)
      } 
      //...Otherwise, render the Index jsx template using the fruits we retrieved
      else {
        res.render('fruits/Index', {
          fruits: foundFruits
        })
      }
    })
  })
  ```

## New
The New route renders form where the client can input the data for creating a new element in our database. Example: if you have a database of fruits and we want to add a new fruit, the new route will display a form template to input the name and color of the fruit.
Uses the GET method for rendering the form. The form, however, uses a POST method. See "create" below.
```
//Use a GET request on endpoint /fruits/new
app.get('/fruits/new', (req, res)=>{
  //Renders the New form jsx template
  res.render('fruits/New')
})
```

## Create
The Create route creates a new element using the data passed on the form in the New route  Example: if you have a database of fruits and we want to add a new fruit, the create route will create a fruit using the name and color given on the new route.
Uses the POST method.

```
//Receives data given in a form, all the data will be inside req.body. express.url on line 14 parses the info and puts it inside req.body 
//Use a POST request on endpoint /fruits
app.post('/fruits', (req,res)=>{

  //req.body contains all the form data from the user
  req.body.readyToEat === 'on' ? req.body.readyToEat = true : req.body.readyToEat = false
  
  //This is a callback. If the creation of the fruit fails, then we send the errors...
  
  //The new fruit value is assigned to the variable createdFruit
  Fruit.create(req.body, (error, createdFruit)=> {
    if(error){
      res.status(400).send(error)
    }
    //...Otherwise, redirect us to the index, which will now have our fruit
    else{
      res.redirect('/fruits')
    }
  })
})
```
## Show
The Show route allows the client to retrieve a specified element in a database, using a unique identifier, like an id.  Example: if you have a database of fruits and we want to retrieve pear, which has an id= 5, the show route will use the id to find all the data associated with the pear fruit.
Uses the GET method.
```
//Use a GET request on endpoint /fruits/:i where :i is the input index by the user
app.get('/fruits/:id', (req, res) => {
//Using Mongoose's method, find, retrieve the specified fruit using the id in req.params.i
  Fruit.findById(req.params.id, (err, foundFruit) => {
  //If there is an error retrieving the fruits, log it
    if(err){
     console.error(err)
     res.status(400).send(err)
    } 
    //...Otherwise, render the Show jsx template using the fruit data retrieved
    else {
     res.render('fruits/Show', {
       fruit: foundFruit
     })
    }
  })
 })
```
