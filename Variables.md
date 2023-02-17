# Variables

### `var`
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
### `let` 
- now preferred for variable declaration. It's no surprise as it comes as an improvement to var declarations. It also solves the problem with var that we just covered.
- let is block scoped
A block is a chunk of code bounded by {}. A block lives in curly braces. Anything within curly braces is a block.

So a variable declared in a block with let  is only available for use within that block. Let me explain this with an example:

```
   let greeting = "say Hi";
   let times = 4;

   if (times > 3) {
        let hello = "say Hello instead";
        console.log(hello);// "say Hello instead"
    }
   console.log(hello) // hello is not defined
```
### let can be updated but not re-declared.
- Just like `var` , a variable declared with `let` can be updated within its scope. Unlike var, a `let` variable cannot be re-declared within its scope.

### Hoisting of let
- Just like  `var`, `let` declarations are hoisted to the top. Unlike `var` which is initialized as `undefined`, the `let` keyword is not initialized. So if you try to use a `let` variable before declaration, you'll get a `Reference Error`.
---------------------------------------
### `const`
- Variables declared with the `const` maintain constant values. `const` declarations share some similarities with `let` declarations.

### const declarations are block scoped
- Like `let` declarations, `const` declarations can only be accessed within the block they were declared.

### const cannot be updated or re-declared
- This means that the value of a variable declared with `const` remains the same within its scope. It cannot be updated or re-declared. So if we declare a variable with `const`, we can neither do this:

```
    const greeting = "say Hi";
    greeting = "say Hello instead";// error: Assignment to constant variable. 
```
nor this:

```
    const greeting = "say Hi";
    const greeting = "say Hello instead";// error: Identifier 'greeting' has already been declared
```

Every `const` declaration, therefore, must be initialized at the time of declaration.

This behavior is somehow different when it comes to objects declared with `const`. While a `const` object cannot be updated, the properties of this objects can be updated. Therefore, if we declare a `const` object as this:

```
    const greeting = {
        message: "say Hi",
        times: 4
    }
```
while we cannot do this:

```
    greeting = {
        words: "Hello",
        number: "five"
    } // error:  Assignment to constant variable.
```
we can do this:

```
greeting.message = "say Hello instead";
```

This will update the value of `greeting.message` without returning errors.