### Data Types
- Boolean – Represents true and false values
- Null – Represents empty, nothing, and unknown type of values
- Number – Represents both integer and floating point values
- Object – Used for storing collections of data or more complex entities
- String – Represents single-character, multi-character, and alphanumeric values
- Symbol – Used for creating unique identifiers for objects
- Undefined – Represents value not assigned. If a variable is only declared and not assigned in JS, then it represents the undefined data type
### Errors in JS
- Eval Error – Thrown when coming across an error in eval() (Newer JS releases don’t have it)
- Range Error – Generated when a number outside the specified range is used
- Reference Error – It comes into play when an undeclared variable is used
- Syntax Error – When the incorrect syntax is used, we get this error
- Type Error – This error is thrown when a value outside the range of data types is tried to be used
- URI Error – Generated due to the use of illegal characters
### apply() and call()
- apply lets you to pass arguments as array
- call you have to explicitly pass arguments seperated by commas
- A for array and c for comma
- Apply uses Arrays and Always takes one or two Arguments. When you use Call you have to Count the number of arguments.
```
function theFunction(name, profession) {
    console.log("My name is " + name + " and I am a " + profession +".");
}
theFunction("John", "fireman");
theFunction.apply(undefined, ["Susan", "school teacher"]);
theFunction.call(undefined, "Claude", "mathematician");
theFunction.call(undefined, ...["Matthew", "physicist"]); // used with the spread operator
```
### Strict
- Strict mode adds certain compulsions to the JS.
- It is used for removing some code mistakes that result in dropped efficiency of JS engines.
### isNaN (isNotaNumber)
- True if not a Number
- False if a number
### = & == & ===
- = assigns value
- == just compares values not data types
    -- 100 == "100" true
    -- 100 == 100 true
- === compares value and data types (strict compare)
    -- 100 === 100 true
    -- 100 === "100" false
### Undefined
- declared but not initialised
- not defined
- property or index not exist
- return value of a function that doesn't return anyting
### Closure
- Closure means inner function has access to variables and parameters of an outer function.
- A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment).
- In other words, a closure gives you access to an outer function’s scope from an inner function.
- To use a closure, define a function inside another function and expose it. To expose a function, return it or pass it to another function.
- The inner function will have access to the variables in the outer function scope, even after the outer function has returned.
### var,let and const
- **Scope**
    -- var global scoped or function scoped
    -- let block scoped
    -- const block scoped
- **Declaring**
    -- var can be redeclared and updated
    -- let cannot be redeclared and but updated
    -- const cannot redeclare and cannot update
    -- const must be initialized during declaration. let and var can be declared without initialization.
- **Hoisting**
    -- Hoisting is a JavaScript mechanism where variables and function declarations are moved to the top of their scope before code execution.
    -- var variables are hoisted to top of its scope and initialiazed with value of undefined
    -- let is also hoisted to top of its scope but not initialized, you'll get *Reference Error* on accessing.
    -- const is also hoisted to top of its scope but not initialized, you'll get *Reference Error* on accessing.
### Currying
- Currying is a technique of evaluating a function with multiple arguments, into sequence of function with single/multiple argument.
- Like we simply turn up add(2,3) into add(2)(3).

### Angular
- Custom directive (tags)
- MVC pattern
- Components
- Directives
- Routing
- static and angular templates
- 2 way data binding
- Dependency Injection
- **Angular 7**
    -- splitting @angular/core to reduce the size of app
    - drag and drop && virtual scrolling
### String interpolation in Angular
- template expressions can be enclosed and evaluated within [{--}]
### Promise
- A promise is an object that may produce a single value some time in the future: either a resolved value, or a reason that it’s not resolved (e.g., a network error occurred).
- A promise may be in one of 3 possible states: fulfilled, rejected, or pending
- Promise users can attach callbacks to handle the fulfilled value or the reason for rejection.
- Promises are eager, meaning that a promise will start doing whatever task you give it as soon as the promise constructor is invoked.
- The ES6 promise constructor takes a function. That function takes two parameters, resolve(), and reject().
```
fetch(url)
  .then(process)
  .then(save)
  .catch(handleErrors)
;
```
### Observers and Promises
- A Promise handles  a single event when an async operation completes or fails
- Promises can gives a single event, observers can give mulitple events
- Observables behave as arrays and can be filtered for specific data
- Observables can be unsubscribed
### Directives in Angular
- They allow an Angular developer to write new, application-specific HTML syntax.
- In actual, directives are functions that are executed by the Angular compiler when the same finds them in the DOM.
- Structural Directives
    -- *ngIf, *ngFor, *ngSwitch
- Attribute Directives
    -- ngClass, ngStyle
- Custom Directives
    -- Highliter, DropDown
### Angular Architecture
![image](https://hackr.io/blog/uploads/images/1570190912nVsPYyUCFu.jpg)
- Angular uses Ahead-of-Time (AOT) compilation
### Data Binding
- connecting application data with DOM, data binding is used
- Event Binding – Enables the application to respond to user input in the target environment
- Property Binding – Enables interpolation of values computed from application data into the HTML
- Two-way Binding – Changes made in the application state gets automatically reflected in the view and vice-versa. The ngModel directive is used for achieving this type of data binding
### ngOnInit()
- ngOnInit() is a lifecycle hook that is called after Angular has finished initializing all data-bound properties of a directive. It is defined as:
```
Interface OnInit {
 ngOnInit() : void
}
```
### Transpiling
- Process by which typescript code gets compiled into equivalent javascript code.
