### Data Types
- Number
- String
- Boolean
- Object
- Undefined
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
