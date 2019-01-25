# WDI Sample Teach: Prototypal Inheritance in Javascript

## Learning Objectives

- Define Prototypes and Inheritance
- Describe how Constructors pass properties to new Objects
- Define a custom Constructor method that sets one or more properties of a new object

## Warm Up

So far, we've worked with variables, objects, and functions in Javascript.

- **How do we define a variable to stores the value of the number 3?**
- **How do we define a variable to stores the value of your first name?**

<details>
<summary>Answer:<br/><br/></summary>

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

But - We never defined these methods, so where do they come from?

## Object Prototypes

In Javascript, there are objects that correspond to each of the basic data types.

- Number
- String
- Boolean
- etc

Whenever we assign one of these values to a variable, as in the examples, these new values _inherit_ properties and methods from these Object Prototypes.

_Prototypical Inheritance_ simply means that objects can pass properties to other objects.

The Object Prototypes themselves inherit from the `Object Prototype` itself, and the diagram of how properties and methods are passed down from object to object is the _Prototypal Chain_.

If we look for a property or method, Javascript will look at that object, and if it cannot find it then it will go up the Prototype Chain and search for it in the _Constructors_.

Question: why might this be useful?

<details>
<summary>A few reasons:<br/><br/></summary>

- reuse methods and properties (DRY)
- flexible: objects can add their own properties
- organization

</details>

We can use Prototypal Inheritance in our own custom objects, too!

## We Do: Object Review

Let's say we want to make a bunch of Objects to represent cars.

What are some good properties for a car?

### How do we assign an object to a variable (literally \*hint hint\*)

<details>
  <summary>Answer:<br/><br/></summary>
  ```js
  var carA = {
    make: 'Camry',
    year: 2010
  }
  ```
</details>

Now, what if we want to make ANOTHER person?

## Constructor Functions

### I Do (but follow along!): 'Car' Constructor Method

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

### We Do: Using the Constructor

<details>
<summary>Answer:<br/><br/></summary>

```js
var camry = new Car('camry', 2010)
```

</details>



let's make another car!

## Improving the Constructor

If we look closely at our new objects, we might see that the `honkHorn` method is duplicated each time.

Bonus: how could we use Prototype methods to check if an object has it's own property, or if it is inheriting it from a constructor?

The Constructor method has a property called `.prototype` that allows us to add methods specifically to the method. That way, we can remove it from the method itself and each time we make a new object, it will then look at the Prototype for that method.

### I do: Refactoring

```js
/** new Car constructor */
function Car (make, year) {
  this.make = make,
  this.year = year
}

Car.prototype.honkHorn = function () {
  alert('HOOOOOOONK!')
}
```

There's a lot to unpack with this code change, let's make sure everyone understands what's happening before we start the You Do

## You Do: Temperature Constructor

### Prompt

Make a Constructor function called Temperature.

#### MVP

1. Give the Constructor two properties:

- a property to store the unit for the temperature (Fahrenheit, Celsius, Kelvin, go nuts!)
- a property to store the value of the temperature

2. Use the Constructor to create two unique Objects

#### Bonus

Give the constructor a method to convert the temperature from one measurement unit to another