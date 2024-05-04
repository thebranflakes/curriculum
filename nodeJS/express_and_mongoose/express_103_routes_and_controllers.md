### Introduction

The next step in the MDN express tutorial sets up all the routes and controllers you're going to need when creating the Library project. This project is designed using the MVC (Model, View, Controller) architecture. In a previous step you set up all the Models (or Database Objects) and in the *next* step you'll be setting up several different views.

If you remember from our earlier lessons, the controller is the code that sits between the models and the views. It determines which view is going to be shown, as well as which information is going to populate that view. In this lesson, you will copy and paste quite a bit of repetitive code to get the controllers and routes set up, but be sure to read everything in between them! There is a *lot* of useful information therein.

### Lesson overview

This section contains a general overview of topics that you will learn in this lesson.

- Create routes.
- Create route-handler callback functions.
- Create a catalog route module.
- Describe approaches for structuring routes and controllers.
- Set up URL endpoints.

### Routes

Routes act as connectors between client requests and controller actions, establishing the URLs and HTTP methods (GET, POST, PUT, DELETE) through which users interact with various features of the application. Each route usually represents a distinct resource or operation within the system, helping with organized and predictable communication between the client and the server.

Example
Consider a simple recipe management application with the following routes:

- GET /recipes: Retrieves a list of all recipes.
- POST /recipes: Creates a new recipe.
- GET /recipes/:id: Retrieves details of a specific recipe.
- PUT /recipes/:id: Updates an existing recipe.
- DELETE /recipes/:id: Deletes a recipe.

When a user sends a GET request to /recipes, the application's router directs the request to the corresponding controller action responsible for fetching all recipes from the database. Similarly, when a user submits a POST request to /recipes, the router invokes the controller action to create a new recipe.

### Controllers

Controllers capture the application logic and handle the processing of incoming requests. They organize the interaction between models (data layer) and views (presentation layer), direct the appropriate response to send back to the client.

Example
Using our recipe management application example from above:

```javascript

// Controller for handling recipe-related actions
const Recipe = require('../models/Recipe');

// Retrieve all recipes
exports.getAllRecipes = async (req, res) => {
    try {
        const recipes = await Recipe.find();
        res.json(recipes);
    } catch (error) {
        res.status(500).json({ message: error.message });
    }
};

```

For this example, the getAllRecipes function handles the retrieval of all recipes.

### Assignment

<div class="lesson-content__panel" markdown="1">

1. Complete ["Part 4: Routes and controllers"](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/routes) of the Local Library tutorial.

</div>

### Knowledge check

The following questions are an opportunity to reflect on key topics in this lesson. If you can't answer a question, click on it to review the material, but keep in mind you are not expected to memorize or master this knowledge.

- [How do you define a route function in Express?](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/routes#defining_and_using_separate_route_modules)
- [Name four HTTP verbs a route might need to handle.](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/routes#http_verbs)
- [What is a route parameter, and what syntax is used to define one in a route handler?](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/routes#route_parameters)
- [What is a route-handler callback function commonly called?](https://developer.mozilla.org/en-US/docs/Learn/Server-side/Express_Nodejs/routes#create_the_route-handler_callback_functions)

### Additional resources

This section contains helpful links to related content. It isn't required, so consider it supplemental.

- It looks like this lesson doesn't have any additional resources yet. Help us expand this section by contributing to our curriculum.
