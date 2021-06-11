# learning-js
Repository of notes and beginner files for learning JavaScript and Node.js 

## INTRODUCTION

### Some basics:
> // this is a comment\
> /* this is a comment as well */\
> console.log('Hello World'); // prints out result in console\
> alert('bruh'); // a pop up with message 'bruh'

You can use semicolons in most circumstances at end of statement but you don't have to.

> console.log('Wow this is cool');\
> console.log('Wow this is cool too')\
> console.log('this errors because statement did not end;

You can have a statement span multiple lines

> console.log(1\
> +\
> 2)  // does not error

## Variables

Declaring a variable:
> let var;

Initializing a variable:
> var = 3;

Do both at the same time:
> let var = 3

Erroring if you use "let" statement on an already declared variable
> let var = 3;\
> let var = 1; // error

## DATA TYPES
### Numbers
Integers and floats; overflows once too big in the positives or negatives.
- 302
- 102
- 0.212 
- 3.1415 
- Infinity
- -Infinity
- NaN (not a number)

> alert(1 / 2); // 0.5\
> alert(1 / 0); // Infinity\
> alert(1 / 0 == Infinity); // true\
> alert("bruh" / 2); // NaN

### BigInt
Large numbers that can does not overflow at Number's limits (similar to long in Java). 

Type **n** at end of number

> alert(9999999999999999999999999999999) // 1e+31\
> alert(9999999999999999999999999999999n) // does not error

### Strings
Text. Can use single or double quotes for Strings.

Use backticks(`) to embed another string in another string. Put ${str} inside the backticks to embed.

> let str = "Hello";\
> let str2 = 'Single quotes are ok too';\
> let phrase = \`can embed another ${str}`;
> alert(phrase);  // "can embed another Hello"

### Booleans
True or false.

> let isChecked = false;\
> let fourGreaterThanTwo = 4 > 2;
> alert(fourGreaterThanTwo); // true

### Null
No type.

> let bruh = null;\
> alert(bruh); // null

### Undefined
What a variable is equal to if it is unassigned.

> let a;\
> alert(a); // undefined\
> alert(a == undefined); // true\
> let b = 11;\
> b = undefined;\
> alert(b); // undefined

### Objects
A type that can have multiple characteristics (discussed later).

### typeof Operator
Returns a **string** of the type of the operand/argument.

> typeof undefined // "undefined"\
> typeof(undefined) // also works\
> typeof 0 // "number"\
> typeof(0) // also works\
> typeof 10n // "bigint"\
> typeof true // "boolean"\
> typeof "foo" // "string"\
> typeof Symbol("id") // "symbol"\
> typeof Math // "object"; built in object for math operations\
> typeof null // "object" \
> typeof alert // "function"

## INTERACTIONS

### alert
Shows a message and waits for the user to press “OK”.

***Returns*** true if OK pressed, returns false if esc/cancel pressed.

>  result = alert("Hello there!");

### prompt

It shows a modal window with a text message, an input field for the visitor, and the buttons OK/cancel.

> result = prompt(title, [default]);

**title** = The text to show the visitor.\
**default** = An optional second parameter, the initial value for the input field.
value: if press OK. 

***Returns*** true if user pressed OK, then; if pressed cancel then return null.

> let age = prompt('How old are you?', 18);\
> alert(\`You are ${age} years old!`); // You are 18 years old!

### confirm
Shows a modal window with a question and two buttons: OK and Cancel.

***Returns*** true if OK is pressed and false otherwise.

> let isAllenCanadian = confirm("Is Allen Cao a Canadian");\
> alert(isAllenCanadian); // true if OK is pressed

## TYPE CONVERSIONS
Most of the time, operators and functions automatically convert the values given to them to the right type.

For example, alert automatically converts any value to a string to show it. Mathematical operations convert values to numbers.

### String Conversion

**alert(value)** automatically converts value to string

**String(value)** converts value to string

> let value = true;\
> alert(typeof value); // boolean\
> value = String(value); // now value is a string "true"\
> alert(typeof value); // string

### Numeric Conversion

Numeric conversion happens in mathematical functions and expressions **AUTOMATICALLY**.

Can also use **Number(value)** to explicity convert value to Number.

NOTE:\
**Number(true) = 1**\
**Numer(false) = 0** 

> alert( "6" / "2" ); // 3, strings are converted to numbers
> let str = "123";\
> alert(typeof str); // string\
> let num = Number(str); // becomes a number 123\
> alert(typeof num); // number\
> space123 = Number("   123   ") // 123

If conversion fails (i.e. Number("Hello World")), then **NaN** is returned.

> let age = Number("an arbitrary string instead of a number");\
> alert(age); // NaN, conversion failed

### Boolean Conversion

Empty values are false:
- 0
- null
- undefined
- NaN
- ""

Non-empty values are true:
- 1
- "Hello World"
- "0"
- "null"

> alert( Boolean(1) ); // true\
> alert( Boolean(0) ); // false

> alert( Boolean("hello") ); // true\
> alert( Boolean("") ); // false