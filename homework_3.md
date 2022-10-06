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

## Show
