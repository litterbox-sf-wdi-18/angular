#Angular

Objectives 

* Setting Context
	* History
	* Compare & Contrast to jQuery
	* MVC
* HTML Setup
* Controller
* Built-in Directives
* Filters
* Models
* Controller helpers (Tabs example)
* CRUD
* Validations
* Custom Directives


#Angular Ref

* [Treehouse](http://teamtreehouse.com/library/angularjs)
* [Intro Angular](https://github.com/sf-wdi-17/notes/blob/master/lectures/week-10/_1_monday/dusk/intro_to_angular.md)
* [8 steps](https://github.com/wdi-sf-fall/intro-to-angular-in-eight-steps)
* [8 steps instructions](https://github.com/sf-wdi-17/notes/blob/master/lectures/week-10/_1_monday/dusk/eight_step_angular.md)
* [Angular Quora](https://github.com/sf-wdi-17/notes/blob/master/lectures/week-10/_4_thursday/dusk/ANGULAR_%E2%99%A5_RAILS.md)



##Intro

[Pre-reading](https://docs.angularjs.org/guide/introduction
)


##jQuery vs Angular

**DOM Manipulation** libraries like jQuery are best for visual polish to already existing data.

**MVC libraries** like Angular are best for maintaining a connection between the HTML view and the data.

##MVC

Angular is an MVC. The...

* `Model` sources and organizes the data
* `Controller` contains logic for a single view
* `View` visualizes the data

##HTML Setup

* Requiring Angular
* App initialization

##Templating

Angular creates it's view by templating directly into HTML with `{{ angularExpressions }}`. This is a declarative way of building the UI.

##Data Binding

####1 way
A joystick on a remote controller for a drone exemplifies 1-way data binding. If the joystick moves, so does the drone; however, if the drone is moved, the joystick does not respond.

![drone-joystick](http://robohub.org/wp-content/uploads/2013/01/ARDroneJoystickControl.png)

####2 way
Quantum entanglement exemplifies two-way data binding. If two electrons are entangled and a change happens to *either*, the other electron's state is updated immediately to reflect the change.

![entangled](http://www.geekpause.com/wp-content/uploads/2014/08/quantum-entanglement1.png)

##Builtin Directives

* `ng-repeat`

##Scope

The interface to pass data into our Views

![scope](http://devgirl.org/wp-content/uploads/2013/03/concepts-controller.png)

##[Filters](https://docs.angularjs.org/api/ng/filter)
Alters the representation of the view. Experiment with: 

* `filter`
* `uppercase`
* `limitTo`
* `orderBy`

##Controllers

Controllers contain the application's business logic, which can be imperatively called on from the View.

##Directives


####Directives to know

In Angular, we add behavior to HTML through directives. A directive is a marker on a HTML tag that tells Angular to run or reference Angular code.

Angular directives start with the prefix `ng-`

`ng-app` turns ordinary HTML into an Angular application.

`ng-model` binds an HTML element's value to a model, bidirectionally (2way).

`ng-repeat` ...

[Cheatsheet](http://www.cheatography.com/proloser/cheat-sheets/angularjs/)


---
####Nice to have

##Factories

* Creates a *singleton* in order to maintain state throughout the application.



