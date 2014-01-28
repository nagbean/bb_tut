###Introduction###

- How websites use to work. 

- How jQuery took use a step closer to single page applications
 
- How Backbone resolves the code organization problem

- Show websites of companies using Backbone. 


##What to expect from this tutorial## 
- Talk about overall goal

- Talk about taking a server or serverless approach

- Talk about the portability of the serverless approach

- Talk about the different sections



##Start Section One, getting started##

- directory structure

- dependencies added to index.html

- let's test that the dependencies work
  - first jquery, 
  - second, underscore
  - third, backbone


- let's say that we can write code in index.html, but remember, we should always seperate concerns. Let's create a javascript exec file for our app. 

- document.ready the code, but don't put all the code in it, follow the jquery pattern 

----------------------------------------------

### Model ###

- directory structure 
- are objects of data 
- let's create a backbone model
- prototype inheritance
- let's make it a generic todo model
- how do we access the properties 
- how we can change the properties 
- how we can all the properties at once

- defaults 

### View ###

- directory structure
- views monitor the dom, what happens, how to change it, etc. 
- let's just focus on the latter for now ,create dom elements 
- let's create a backbone view
- same type of prototype inheritance

- let's talk about default el 
- let's talk about render 
- then let's create an instance of el 
- console.log it

- let's refactor a bit, and put the dom element in an html var first 
- let's use a template engine

--------------------------

### Model and View ###
- HOW AN OBJECT INFLUENCES A VIEW
- now how do we display the object in a view? 
- pass the model as an argument
- then we can reference it with this

- this works, but it's messy 
- let's refactor to get the html out of the current place
- let's place it in a variable called template
- now the code is seperated a little better, bu there still is concatenation 

- this is where the underscore library comes in, in particular the template method
- it saves use from concatinating 
- let's update the template property to ues it
- now we can reference just the property name

- however, their is an additional step of passing in an object to the template

-----------------------------------------------------------
- HOW AN VIEW INFLUENCES AN OBJECT

- let's create another one, but let's do it from the command line.
- this works, but how do we do it from the app itself
- the first step is to create a form 
- now, when we click submit, what should happen? 
- an object should be created, and then the object should be displayed
- let's do this from the command line again with a sample text

- great, now let's add the code and a console.log to confirm this is being executed
- NOTHING
- the problem is that we need to invoke this function when the submit button is clicked
- how do we LISTEN to this click event? 

-------------------------------------------------------------
- Events Hash

- the answer lies in the events property of a view 
- this property alows use to listen to pre-defined events 
- let's see how this works

- let's get back to the submit button, this is the structure for it
- viola, this works for us. 

- now let's explore the events hash a little more
- let's add chechboxes to our items
- when the box is checked, let's change the view and change the model 
- remember, we want to get the view to change the object


+++
- but let's take this one step at a time
- we are trying to do two things, change the text and change the object

- let's start with the first
- we can add a class to achieve this
- a good approach is use a mode prop's value, status
- let's try from console
- good

- now, when an object's status changes, the text changes
- when do we want the object to change, what event is causing it? 
- the checkbox being checked
- let's create an event for it and use console.log to test it
- it works 
- now we can say within it, we can use a conditional
- we can console.log the status to confirm
- it does work, but why isn't the text being updated

- well, we need to tell the template engine to add the status as a class
- boom, done. 


--------------------------
REFACTOR RENDER

- now there is an issue here that we can see in the future, if we create another view that cna change the status, it won't trigger this render call, so we need to refactor to look for any change to the status, not a particular event
- we can tell the view to listen for any changes to the model's status, and this will work better
- the approach is to use an initalize method, which runs when an instance is created
- let's see the benefit of this and create an X for destroy 


- that's it, this is a basic introduction to models and views

---------------
------------------------
------------------------------

### Routes, Collections, and Views ###

- we have some meaningful progress 
- but more can be done
- if we want to see details about one, how can we do that
- what if we want to see all of the tasks at once?

### COLLECTIONS ###
- let's start with going to a homepage with all our todo history
- we want the following to happen, visit a root url, then see all todo items
- let's first start with the concept of viewing ALL items
- we want to view all collections, which is a model in backbone
- let's explore it in console.log
- ...
- so now we know how to view them all, which is iteration

### ROUTES ###
- so far, we have only one page, how do we scale if we want to add more pages
- we need to create a route 
- let's see how this is done
- ...
- great, it works 

- let's play with routes some more
- let's start with exploring a item further
- let's add a memo property
- let's add a field for it
- now, let's add an event for when the title is clicked
- we will add some css to this
- now, this is a single page application, but we would for bookmarking purposes,  want to see a url, a real one

- how do we do it? 
- pretty simple, right? 


-------------------------------------------

- now, if we delete an object, how do we delete all related items, like the template page/route for it



---------------------

- things that weren't covered
- validations 










