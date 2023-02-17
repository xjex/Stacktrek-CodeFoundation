# Code Foundation Javascript

---------------------------------------

## Printing "Hello World!" to console
```
console.log("Hello World!")
```
---------------------------------------

## Commenting in JavaScript

Comments can be done by putting "//" two slashed at the front of the text 
```
//this is a comment...
```
this will not do anything since it is just a comment 

---------------------------------------
## Variables

### var
- declarations are globally scoped or function scoped
- var variables can be re-declared and updated
```
var greeter = "hey hi";
var greeter = "say Hello instead";
```

and this also

```
var greeter = "hey hi";
greeter = "say Hello instead";
```

### Hoisting of var
Hoisting is a JavaScript mechanism where variables and function declarations are moved to the top of their scope before code execution. This means that if we do this:

```
    console.log (greeter);
    var greeter = "say hello"
```

it is interpreted as this:

```
    var greeter;
    console.log(greeter); // greeter is undefined
    greeter = "say hello"
```
So var variables are hoisted to the top of their scope and initialized with a value of undefined.

#### Problem with var
- There's a weakness that comes with  var. I'll use the example below to explain:

```
var greeter = "hey hi";
    var times = 4;

    if (times > 3) {
        var greeter = "say Hello instead"; 
    }
    
    console.log(greeter) // "say Hello instead"

```
So, since times > 3 returns true, greeter is redefined  to "say Hello instead". While this is not a problem if you knowingly want greeter to be redefined, it becomes a problem when you do not realize that a variable greeter has already been defined before.

If you have used `greeter` in other parts of your code, you might be surprised at the output you might get. This will likely cause a lot of bugs in your code. This is why `let` and `const` are necessary.

---------------------------------------
### let 
- now preferred for variable declaration. It's no surprise as it comes as an improvement to var declarations. It also solves the problem with var that we just covered.


---------------------------------------