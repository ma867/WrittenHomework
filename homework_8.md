## What are all the JavaScript Data Types?
Null, Undefined, String, Number, Boolean, BigInt, Symbol

## What is the Difference Between Const Let and Var? Consider Scope ... Give an example
Const - block scoped (variable declared in a block with let  is only available for use within that block), value cannot be updated or redeclared

Let - block scoped (variable declared in a block with let  is only available for use within that block), value can be changed and redeclared

Var - exists in the local and global scope

## Pass By Value vs Pass By Reference? Why would you say a String is pass by value/ or a value type? Why is an object a reference type?
Pass by value: The method parameter values are copied to another variable and then the copied object is passed to the method. The method uses the copy. Pass by reference: An alias or reference to the actual parameter is passed to the method

A string is a primitive type whereas an object is a non-primitive type. Since non-primitive types are mutable, they are passed by reference.

## What do Map , Filter and Reduce do? Do they mutate the array you call them on?

### Map: Using map you iterate the elements, and for each element you return an element you want.

```
// A function which calculates the square
const square = x => x * x

// Use `map` to get the square of each number
console.log([1, 2, 3, 4, 5].map(square))```

```
### Filter: tests every element of an array against a callback function, returning all elements that pass the test.
```
const firstFibs = [0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233];
const fibsUnder100 = firstFibs.filter((fNum) => fNum < 100);
// [0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89]
```

### Reduce: The reduce() method reduces an array of values down to just one value. To get the output value, it runs a reducer function on each element of the array.

```
const numbers = [1, 2, 3, 4];
const sum = numbers.reduce(function (result, item) {
  return result + item;
}, 0);
console.log(sum); // 10
```
## What are all the Falsey Values in JavaScript? Why do you think this is important to know?
Value that will return false in a boolean context.


## What are Async and Await?
The word “async” before a function means one simple thing: a function always returns a promise. The "await" keyword makes the function pause the execution and wait for a resolved promise before it continues.

## What is an async function?
## What are try and catch?
