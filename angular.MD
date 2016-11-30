Angular Notes
===========

For extending HTML
-----------

### ng-app="" 
> directive that tells angular that the element is the owner of the angular JS application
>> used for init angualar on a page. Used on the pages parent div
 
### ng-model="example" 
> binds the value of the input field to the application variable name
>> ties the html element to the angualar variable
>> input
 
### ng-bind="example" 
> binds the innerHTML of the element to the application variable name
>> outputs that angualr variable
 
<div ng-app="">
    <h1> HTML Extend</h1>
    <p><input type="text" ng-model="name"></p>
    <p ng-bind="name"></p>
    <h1>Expressions</h1>
    <p>First Expression {{ 5 + 5 }}</p>
</div>
 
- use data-ng-app instead of ng-app if you want to mke the page HTML valid

Expressions
-----------

### {{example}}
> expressions are written inside of double braces
    
### ng-bind="expression"
> can also be written inside of a directive

<div ng-app="">
    <h1>Expressions</h1>
    <p><input type="text" ng-model="name"></p>
    <p ng-bind="name"></p>

    <h1>Expressions</h1>
    <p>First Expression {{ 5 + 5 }}</p>

    <h1>Using bind for a directive</h1>
    <p>Name: <input type="text" ng-model="expressionBind"></p>
    <p>{{expressionBind}}</p>
</div>

- expressions bind AngularJS data to HTML the same way as the ng-bind directive
- Angular will resolve the expression, and return the result exactly where the expression is written
- expressions can contain the following
    + literals
    + operators
    + variables
- you cannot use the following naming convention for expressions
    {{expression-bind}}
- if you remove the ng-app directive, the HTMl will display the expression as it is, without solving it

Angular applications
-----------

### Module : module defines applications
var app = angular.module('myApp', []);

### Controller : controls applications

app.controller('myCtrl', function($scope) {
$scope.firstName= "John";
$scope.lastName= "Doe";
});
 
<div ng-app="myApp" ng-controller="myCtrl">
     <h1>Applications / Controllers</h1>
     <p>First Name: <input type="text" ng-model="firstName"></p>
     <p>Last Name: <input type="text" ng-model="lastName"></p>
     <br>
     <p>Full Name: {{firstName + " " + lastName}}</p>
</div>
<script>
     var app = angular.module('myApp', []);
     app.controller('myCtrl', function($scope) {
     $scope.firstName = "John";
     $scope.lastName = "Smith";
     });
</script>


Last Link
---------------

http://www.w3schools.com/angular/angular_expressions.asp
