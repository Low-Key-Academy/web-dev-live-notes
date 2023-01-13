# Intro to JavaScript
JS is a high-level, loosely-typed, general-purpose, multi-paradigm programming language that is one of the few programming languages natively understood by web browsers.

## Logs and Comments
Comments are for developers only, and are specifically not executed by the translator.

Logs are also for developers only, and are executed in order for the developer to gain knowledge about their program.

```js
// this is JavaScript
console.log("hello world");
```

```python
# this is python
print("hello world")
```

```cs
// this is C#
Console.WriteLine("hello world");
```

## Variables and Data Types
JavaScript has a handful of built-in data types. We can store data in memory by using "variables".
Since javascript is "loosely-typed" we can store any type of data in any variable.
```js
// to create a new variable, use the let keyword followed by the variable's name
// the name can be almost anything, as long as it follows a few rules
// no spaces, must start with an alphanumeric character, some special characters won't work
// variables store information in memory (RAM) until they are no longer needed by the program
// a single '=' in js is _always_ assigning/storing a value somewhere

// built-in data types are:
// numbers
// can be positive, negative, integers, or fractional with a decimal point
let myNumber = 10;

// strings
// a specific sequence of characters in a specific order
// can use single or double quotes interchangeably
// use \ to escape "special characters", in other words, ignore the default functionality of the next character
let myString = "This is a really long string that I don't want to have to type again a million times and that's why I'm storing it here."
let mySpecialString = 'I like using single quotes but I can\'t use them because there\'s a few contractions in this sentence';

// booleans
// true or false
let myBoolean = true;

// null, undefined
// specifically the intentional or unintentional absence of data
let myUndefined = undefined;
let myNull = null;

// arrays
// an ordered collection of any data type, indexed by 0
let myArray = ['hi', 3, "yo", false];
console.log(myArray[0]);

// objects
// an unordered collection of key/value pairs
let myObject = {
  name: "Wes",
  age: 28
}
```

### Overwriting Values
Variables defined using the `var` or `let` keyword can be freely overwritten.

```js
let myNumber = 10;
myNumber = "Something new";

console.log(myNumber);

// the right side of the assignment operator "=" can be somewhat complex
// for instance, to add 1 to an existing variable (storing a number), each of the following is possible

let num = 10;

// this says "take the container named 'num' and replace it with the current value of 'num', plus one"
num = num + 1;
// this is a shorthand of the above
num += 1;
// this is even shorter, but only ever adds exactly 1
num++;
```

## Conditionals and Comparisons
Conditionals allow us to "conditionally" execute code based on certain conditions.

```js
// imagine myNumber comes from a remote source and we don't know what its actual value is
let myNumber = 10;


// an "if" statement allows us to run code if a condition is true
// any comparison operator will produce a boolean outcome
if(myNumber > 100) {
  console.log("the number is greater than 100");
}

// optionally, we can use either the "else if" or "else" keywords to add additional cases
// they cannot exist without a corresponding "if" statement and are run in order
// only the first "truthy" conditional statement will run

// the following have different outcomes
if(myNumber > 100) {
  console.log("the number is greater than 100");
} else {
  console.log("the number is less than or equal to 100");
}

if(myNumber > 100) {
  console.log("the number is greater than 100");
} else if(myNumber === 10) {
  console.log("the number is equal to 10");
} else {
  console.log("the number is less than or equal to 100");
}

// available comparators are ===, ==, !==, !=, <, <=, >, >=
// for now, always use === and !==

// we can combine boolean expressions by using logical "and" && and "or" || statements
if(myNumber > 100 && myNumber !== 1000) {
  console.log('The number is high, but thank goodness it isn\'t 1000')
} else {
  console.log('This is a bad number');
}
```

## Loops
Loops allow us to repeat the same task over and over. However, we have to be careful because the computer will execute our code as written, so we need to ensure that the program will eventually stop.

```js
// while loops execute the associated code block while the boolean expression given is still true
// the conditional is re-checked at the end of the code block and start over if necessary
let i = 0;
while(i < 255) {
  console.log(i);
  i++;
}

// careful, this will be an infinite loop. Why?
let i = 0;
while(i < 255) {
  console.log(i);
}

// for loops are useful when we know exactly how many iterations we'd like to do
// they allow us to specify different statements on the same line for easier reading
// the first statement is usually the declaration of a new variable
// the second is a boolean expression similar to the one in a "while" loop
// the third is an action that will happen after each iteration of the loop
for(let i = 0; i < 255; i++) {
  console.log(i);
}
```

## Functions and Code Blocks
Functions are like variables for blocks of code. They store functionality in memory to be used later. They can specify multiple inputs and a single output.

```js
// to declare a function, use the function keyword followed by the function name
// the same naming rules apply to functions and variables
// the parentheses and curly braces are always required
function myFunc() {
  console.log('hello world');
}

// functions are storing code to be run later, but will not run automatically
// to run the code inside the function's code block, we need to "call"/"invoke"/"run" the function
// we do this by referring to the function by name followed by open and closed parentheses
myFunc();

// if the function needs one or more inputs (often called arguments or parameters), we define them inside the parentheses in the function definition statement
function myFuncWithInputs(inputOne, inputTwo, inputThree) {
  console.log(inputOne);
  console.log(inputTwo);
  console.log(inputThree);
}

// to send a value into the function as an input, pass the value in the function invocation
myFuncWithInputs(1, 2, 3);

// inside any code block can be any statement or expression, including statements and expressions that require their own code block
function myConditionalFunction(input) {
  if(input > 3) {
    console.log("greater than 3");
  } else {
    console.log("less than or equal to 3");
  }
}
myConditionalFunction(10);

// a function's output is determined by its 'return' statement
// the return statement will end execution of the function and return to the previous location

function funcWithOutput() {
  console.log("function is being called");
  return 10;
  console.log("this will never run because it's after the return");
}

console.log('hello world');
// a return statement does not print
funcWithOutput();
// we can either store the value in a variable
let output = funcWithOutput();
console.log(output);
// or print it directly
console.log(funcWithOutput());
```