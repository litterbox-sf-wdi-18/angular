#Angular

| **Learning Objectives** |
| :---- |
| Comprehend the philosophy of Angular |
| Setup an Angular project |
| Write expressions |
| Implement data binding |
| Leverage built-in filters |
| Leverage built-in directives |
| Conceptualize and use $scope |


#Prereading Highlights

[Angular Guide Introduction](https://docs.angularjs.org/guide/introduction
)

* A "framework for dynamic web apps"
* "Lets you use HTML as your template language"
* Will "extend HTML's syntax"
* "Handles all of the DOM and AJAX glue code you once wrote by hand and puts it in a well-defined structure"
* Is "opinionated about how a CRUD application should be built"
* Comes with "Data-binding, basic templating directives, form validation, routing, deep-linking, reusable components and dependency injection"
* "Angular simplifies application development by presenting a higher level of abstraction to the developer"
* "Not every app is a good fit for Angular. Angular was built with the CRUD application in mind."
* "Angular is built around the belief that declarative code is better than imperative when it comes to building UIs and wiring software components together, while imperative code is excellent for expressing business logic."

##HTML Setup

Head to [jsbin](http://jsbin.com/) and setup a new workspace.

Add Angular 1.4 to the project with the `Add Library` button

In your HTML try changing the `<body>` to `<body ng-app>`. This will tell your HTML page to use use Angular.

Let's name our app `ngFun`. To do this we can create an empty angular module.

```js
var app = angular.module("ngFun", []);
```

Now update your `body` element to `<body ng-app="ngFun">`.

Sweet we're up and running!

##Templates & Expressions

Angular creates it's views by templating directly into HTML with expressions. This is it's declarative way of building the UI.

Try writing any regular javascript expression in side double curly brackets, such as: `{{ <expression> }}` and see what your HTML evaluates to. What happens what you express:

* `4 * 4`
* `"hola!".toUpperCase()`
* `['s','w','e','e','t','n','e','s','s'].join("")`

##Controllers & Scope

Controllers contain all the business logic for our application.

We can seed our application with some data, but first we have to create a controller.

```js
app.controller("PokemonCtrl", function() {
	//logic here
});
```

Most applications will have several controllers that map to a particular resource. In this case we're using Pokemon.

To use our controller somewhere in our View we have to declare it. Create a new `div` tag that will house our Pokemon Controller.

```
<div ng-controller="PokemonCtrl">
	<!--placeholder for now-->
</div>
```

In order to pass data or behavior to our HTMl view we need to use the object `$scope`. It is the interface to pass data and behavior into our views. Both the View and Controller share access to the $scope object.

![scope](http://devgirl.org/wp-content/uploads/2013/03/concepts-controller.png)

Let's register some Pokemon with $scope!

```js
app.controller("PokemonCtrl", function($scope){
  $scope.pokemon = [
    {
      Ndex: 25,
      name: 'Pikachu',
      type: 'Electric'
    },
    {
      Ndex: 10,
      name: 'Caterpie',
      type: 'Bug'
    },
    {
      Ndex: 39,
      name: 'Jigglypuff',
      type: 'Fairy'
    },
    {
      Ndex: 94,
       name: 'Gengar',
      type: 'Ghost'
    },
    {
      Ndex: 143,
      name: 'Snorlax',
      type: 'Normal'
    }
  ];
});
```

Great, now let's see if we can see them in our view by referencing the `pokemon` variable inside an expression and wrapping it in a `pre` tag.

```
<div ng-controller="PokemonCtrl">
	<pre>{{ pokemon }}</pre>
</div>
```

That's cool, but it doesn't look very great. What if we could format our data so that the View knows to render it as JSON?

###Challenge

1) Try using an Angular [filter](https://docs.angularjs.org/guide/filter) to render the data as JSON! Here are a [list](https://docs.angularjs.org/api/ng/filter) of options you can implement.

2) Pass a new variable `catchphrase` from the Controller to the View. Set it's value as "gotta catch 'em all!" and use an angular filter to uppercase it in the View.


##[Directives]

In Angular, we add behavior to HTML through directives. A directive is a marker on a HTML tag that tells Angular to run or reference Angular code. You've already used several!

Angular directives start with the prefix `ng-`

A few we already know:

`ng-app` turns ordinary HTML into an Angular application.

`ng-controller` registers a controller for a section of our application.

A few worth introducing:

`ng-model` binds an HTML element's value to a model.

`ng-repeat` iterates over a collection.


###ng-Model

Our user wants to be able to input their name in a field, so that the application acknowledges them as the trainer for these Pokemon.

Above our list of Pokemon, but still inside our `PokemonCtrl` `div` tag, let's create an input field for our trainers name.

```
  <div ng-controller="PokemonCtrl">
  
    <span>Enter your name:</span>
    <input/>
    
    <pre>{{ pokemon | json }}</pre>
    
  </div>
```

If we want our input field to map it's value to a variable called `trainer` we could add an `ng-model` directive to it.

```
<input ng-model="trainer"/>
```

Additionally if we want the value of the `trainer` variable to be printed on onto our page in an `h1` tag, we can reference it in an expression, such that our HTML looks like:

```
  <div ng-controller="PokemonCtrl">
  
    <h1>Trainer: {{trainer}}</h1>
    
    <span>Enter your name:</span>
    <input ng-model="trainer"/>
    
    <pre>{{ pokemon | json }}</pre>
    
  </div>
```


###Challenge

How could we create a default value for the `trainer` so that when the page loads it is set to `Ash`?

###ng-repeat

`ngRepeat` is a very useful directive for rendering a collection while writing a minimal amount of HTML.

###Challenge

Rendering the JSON Pokemon in a bootstrap table, where each attribute is a column. The final result should look like this:

<!--result-->

Hint: add bootstrap into your project by clicking `Add Library`

###etc

There are many more directives. It is good to know that they exist and which ones are useful in what situations. Beyond that, it totally fine to rely on referencing the documentation. You can find a comprehensive list [here](https://docs.angularjs.org/api/ng/directive).



###Challenge

1) Sort the Pokemon by nDex number.
2) Create an input tag so that I can search for a particular Pokemon.


##Protip: Minification

...

##Bonus: Custom Filters

...


##HW Exercise
* [8 steps instructions](https://github.com/sf-wdi-17/notes/blob/master/lectures/week-10/_1_monday/dusk/eight_step_angular.md)




