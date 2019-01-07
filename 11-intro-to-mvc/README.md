## Mod 2 - How the hell do servers even?

### Mod 2 (a preview) - 5 minutes

#### Week 1

* Learn about HTTP, Requests and Responses
* Learn basics of Routing
* Learn how to write methods to _Respond_ to a _Request_
* Learn how to build views with HTML templates
* Learn how to construct Forms and handle Params





#### Week 2

* Take all the above concepts and see how to use them in Rails
* Pick up some nice Rails helpers to make our lives easier
  * Fall back on "the simple way" if Rails isn't making things easier


#### Today: We Build...

  A tiny library.

  * make a wonderful homepage
  * list all the books
  * get info on a single book
  * tomorrow: maybe add some very good doggos to our library? 😍

### Getting Familiar with HTTP - 10 minutes

* View http://blog.kingcons.io in browser
* `curl http://blog.kingcons.io`
  * now do it with -v
* inspect the Network tab. wow! same thing!
* NOTE: there are other HTTP _verbs_ besides GET
  ... but we'll get to them tomorrow :)
* Important question: What happens after a response is sent?
  * THE SERVER CLOSES THE CONNECTION!


#### Important Status Codes

* 200
* 202
* 204
* 301
* 404
* 401
* 403
* 422
* 500

#### Parts of a Request
- Verb
- Path
- Headers
- Body (optional)

* NOTE: Verb + Path == Route

#### Parts of a Response
- Status Code
- Headers
- Body

### Intro to Sinatra

What's the purpose of Sinatra? What does it do for us?

* Make it easy to build simple web servers

#### Tour of a sinatra app - 5 minutes
* app folder is where most of the excitement is
* config for initial setup
* db mostly interesting when we're adding new migrations
* config.ru?
* shotgun?

#### Defining Our First Route - 5 minutes
* How do we connect actions in our app to pages?
  * Routes connect actions in our app to pages!
  * Example of a route: `GET '/about'`
    * A _Controller method_ is a snippet of code that runs to
      build the response for a _specific route_.
    * Routes and handlers together tell us how to generate them
      response for a specific request.

#### Defining our first View - 10 minutes
* How do communicate between our controller and our view?
  * ERB? Ahhhh. (Don't worry. It's just a templating language.)
  * A template is just a fancier version of string interpolation.
    * String interpolation lets us run snippets of code to fill in parts of a string.
    * Templates exist because we want to customize really big complicated strings. Like web pages! So we take the string and just stuff it in its own file.
  * So, what variables/methods are in scope in a view? 🤔🤔🤔

  * NOTE: Use instance variables for data you need to access from ERB.
  * To print things in ERB: `<%= 2 + 2 %>`
  * To run things but not print in ERB: `<% books = Book.all %>`

#### Putting the Pieces Together - 10 minutes
* Create some books manually.
* Make a route to view an individual book.
* Link back to the homepage?
* Link to all the library books on the homepage.

#### So what is MVC? - 5 minutes
* What is the core idea of MVC?
  * Model-View-Controller, an architectural pattern
  * Splits the responsibility of our app up:
    * Models: manage the data
    * Controllers: that have the application logic
    * Views: that present an interface to the user
  * Code can easily get too messy if these are in the same file,
    let alone the same method. So break them into different parts!
