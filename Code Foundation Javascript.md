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
---------------------------------------
## Variables

### var
- declarations are globally scoped or function scoped
- var variables can be re-declared and updated

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

### let 
- are block scoped


---------------------------------------