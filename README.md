# Objectives
1. Practice refactoring JavaScript code to use more modern syntax
2. Practice destructuring an object
3. Practice converting normal functions into arrow function expressions
4. Examine using for..in  syntax with objects
5. Practice using for..of syntax with arrays
6. Examine code using the spread operator

# Technologies Used
- VSCode

# Part 1
Create two files called lab-03.js and lab-03-module.js in your cit281/p3 folder.

# Part 2
Create vin and year variables using object destructuring.

# Part 3
Create arrow function expression getCarMakeModelImplicit and template literal that returns the same formatted car info as
getCarMakeModel(). The arrow function MUST NOT use a return statement (use implicit return). Include a console.log statement similar 
to getCarMakeModel, but increment the number from 0 to 1.

# Part 4
Create arrow function expression getCarMakeModelExplicit and template literal that returns the same formatted car info as getCarMakeModel(). 
The arrow function MUST use a return statement (use explicit return). Include a console.log statement similar to getCarMakeModel, but increment 
the number from 0 to 2.

# Part 5
Create arrow function expression getCarMakeModelDestructure and template literal that returns the same formatted car info as getCarMakeModel(). 
The arrow function MUST destructure the car properties, which will also require using an explicit return. Include a console.log statement similar 
to getCarMakeModel, but increment the number from 0 to 3.

# Part 6
Study the following code that will list all properties of an object using for..in syntax. The listing will include inherited properties, so the
hasOwnProperty() method is used to only list properties defined in the current object.

# Part 7
Display all array values using for..of syntax.

# Part 8
Reference the following website to use the spread operator to reverse the string for reverseString(str) function. Comment out the
original return line of code.

# Part 9
Add the reverseString function to the module.exports object for import using require().

# Part 10
Add an anonymous function concatenateString that takes a string as a parameter, and returns the original concatenated to itself.

# Part 11
Import reverseString() and concatenateString() functions from lab-03-module.js module using require().

# Part 12
Import and use reverseString() and concatenateString() in a single line of code to produce the following output to the console: cbacba.

# lab-03-module.js
```
// Part 9

// Part 10
module.exports = {
    reverseString, 
    concatenateString: function(inputString) {
        return inputString + inputString;
    }
};

// Part 8
// https://betterprogramming.pub/5-ways-to-reverse-a-string-in-javascript-466f62845827
function reverseString(str) {
    return str.split("").reverse().join("");
}
```

# lab-03.js
```
// Part 11
const { reverseString, concatenateString } = require("./lab-03-module.js");

// Declare a specific car object
let car = {
    make: "Ford",
    model: "Mustang",
    vin: "4S3BMHB68B3286050",
    color: "Red",
    year: 2019,
    mileage: 1234,
    used: true,
    owners: [
        { last: "Last1", first: "First1" },
        { last: "Last2", first: "First2" }
    ]
}

// Part 2
const {vin, year} = car;

// Declare a normal function that returns formatted car info
function getCarMakeModel(car) {
    return car.make + " " + car.model;
}
console.log(0, getCarMakeModel(car));

// Part 3
const getCarMakeModelImplicit = (car) =>  `${car.make} ${car.model}`;
console.log(1, getCarMakeModelImplicit(car));

// Part 4
const getCarMakeModelExplicit = (car) => {
    return `${car.make} ${car.model}`
};
console.log(2, getCarMakeModelExplicit(car));

// Part 5
const getCarMakeModelDestructure = (car) => {
    const {make, model} = car;
    return `${make} ${model}`
};
console.log(3, getCarMakeModelDestructure(car));

// Part 6
for (let prop in car) {
    if (car.hasOwnProperty(prop)) {
        console.log(prop);
    }
}

// Display all values of an array
const primes = [2,3,5,7,11];
// for (let index = 0; index < primes.length; index++) {
//    console.log(primes[index]);
// }

// Part 7
for (const primes of [2,3,5,7,11]) {
    console.log(primes)
}

// Part 12
console.log(concatenateString(reverseString("abc")));
```

[Return to Homepage](https://pozawa1.github.io/)
