# WDI Sample Teach: Protypal Inheritance in Javascript

## Learning Objectives

- Explain how Javascript Objects inherit properties through Prototypes
- Demonstrate a use case that explains prototypal inheritance and `what kind of flexibility it gives to programmers
- Define a custom constructor method that sets one or more `properties of a new object

## Review

So far, we've worked with variables, objects, and functions in Javascript.

- **How do we define a variable to stores the value of the number 3?**
- **How do we define a variable to stores the value of your first name?**

<details>
<summary>
Answer:
</summary>

```js
var num = 3
var firstName = 'Hammad'
```

</details>



We might have seen in earlier exercises that there are methods we can call on these variables.

```js
console.log(num.toFixed(2))
// -> 3.00

console.log(firstName.charAt(1))
// -> 'a'
```

We never defined these methods, so where do they come from?

## Object Prototypes

In Javascript, there are objects that correspond to each of the basic data types.

- Number
- String
- Boolean
- etc

Whenever we assign one of these values to a variable, as in the examples, these new values _inherit_ properties and methods from these Object Prototypes. 

The Object Prototypes themselves inherit from the `Object Prototype` itself, and the diagram of how properties and methods are passed down from object to object is the _Prototypal Chain_.

If we look for a property or method, Javascript will look at that object, and if it cannot find it then it will go up the Prototype Chain and search for it in the _Constructors_.

### How could prototypes be useful in our programs?

- automatically add methods and properties to objects (`toUppercase()`)
- have the flexibility to add and even overwrite properities in Objects if we need to.

We can use Prototypal Inheritance in our own custom objects, to!

## We Do: Object Review

Let's say we want to make a bunch of Objects to represent cars.

What are some good properties for a car?

### How do we assign an object to a variable (literally \*hint hint\*)

<details>
  <summary>Answer:</summary>
  ```js
  var carA = {
    make: 'Camry',
    year: 2010
  }
  ```
</details>





Now, what if we want to make ANOTHER person?

## Constructor Functions

### I Do: 'Car' Constructor Method

```js
function Car (make, year) {
  this.make = make,
  this.year = year,
  this.honkHorn = function () {
    alert('HOOOOOOONK!')
  }
}
```

**Note**: by convention, we capitalize the first letter in Constructors.

### We Do: Using the function


<details>
<summary>Answer:</summary>

```js
var camry = new Car('camry', 2010)
```

</details>



let's make another car!

<!-- moving the method out to the prototype -->

<!-- You Do: Temperature Constructor -->