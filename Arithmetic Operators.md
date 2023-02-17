## [Arithmetic Operators](https://www.w3schools.com/js/js_arithmetic.asp)

| Symbol | Description |
| ----------- | ----------- |
|`+` | Addition|
|`-` | Subtraction|
|`*` | Multiplication|
|`**` | Exponential(ES2016)|
|`/` | Division|
|`%` | Modulus(Remainder)|
|`++` | Increment|
|`--`| Decrement|

A typical arithmetic operation operates on two numbers.

The two numbers can be literals:

```
    let x = 100 + 50;
    console.log(x)
```
or variables:

```
    let x = 100
    let y = 50
    let z = x + y
    console.log(z)
```
or expressions:

```
    let a = 1
    let x = (100 + 50) * a;
    console.log(x)
```

### Addition
The addition operator (`+`) adds numbers:

```
    let x = 100
    let y = 50
    let z = x + y
    console.log(z)
```

### Subtraction
The subtraction operator (`-`) subtracts numbers.


```
    let x = 5
    let y = 2
    let z = x - y
    console.log(z)
```

### Multiplication
The multiplication operator (`*`) multiplies numbers.


```
    let x = 5
    let y = 2
    let z = x * y
    console.log(z)
```

### Division
The division operator (`/`) divides numbers.


```
    let x = 5
    let y = 2
    let z = x / y
    console.log(z)
```

### Remainder/Modulus
The modulus operator (`%`) returns the division remainder.


```
    let x = 5
    let y = 2
    let z = x % y
    console.log(z)
```


### Incrementing
The increment operator (`++`) increments numbers.


```
    let x = 5
    x++
    console.log(x)
```

### Decrementing
The cecrement operator (`--`) increments numbers.


```
    let x = 5
    x--
    console.log(x)
```

### Exponential
The cecrement operator (`**`) increments numbers.


```
    let x = 5;
    let z = x ** 2;
    console.log(z)
```

x ** y produces the same result as Math.pow(x,y):

```
let x = 5;
let z = Math.pow(x,2);
```

## Operator Precedence
Operator precedence describes the order in which operations are performed in an arithmetic expression.

```
    let x = 100 + 50 * 3;
    console.log(x)
```

## Using Parenthesis
The operations inside the parentheses are computed first

```
    let x = (100 + 50) * 3;
    console.log(x)
```

When many operations have the same precedence (like addition and subtraction or multiplication and division), they are computed from left to right:

```
let x = 100 + 50 - 3;
```

```
let x = 100 / 50 * 3;
```