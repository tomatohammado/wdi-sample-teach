# Notes

Start with review -

actually, let me roll it back.

so far, when we’re working with variables in Javascript, we might have seen some methods like .`toFixed()` for Numbers and `charAt()` for Strings

where do these methods come from?

In javascript, there is a concept called Prototypes that happens behind the scenes that not only allows us to call useful methods like this, 

(but to use prototypes to create new, reusable objects with their own respective methods. <- can mention later

In short, all of the Data types in Javascript have a corresponding Object Prototypes

(example), going back to Numbers and Strings
useful methods: `hasOwnProperty`, `constructor`, and `__proto__` for objects specifically 

NOTE: what about functions?
- first class objects, can have properties and methods. Notably, functions can be _called_

and all of these inherite properties from the Object prototype, and these relationships represent the Prototype Chain.

FLEXIBILITY: we automatically have things we need, and can easily add more methods and properties as needed

CHECK IN

now, lets look at Objects

We Do: How do we define an object with a key for name, and the value is your name?

`let obj = { name: 'Hammad' }`

nice, now how can we add a property, called `greeting` that just console.logs “hello”)

(do that)

cool, so now we have one object that has a property and a method.

CHECK IN

but lets say we want to create another person, repeating the process multiple times would be incredibly time consuming.

There is a pattern called constructor functions that allow us to define reusable objects and use Prototypal Inheritance to easily make related individual instances of that object with unique methods.

We Do: let’s start with a car. What properties might a Car have?

(get ideas)

and let’s also say we want to give it a honk method.

awesome, so a constructor method might look like

```js
function Car (name, make, year, color) {
  this.name = name
  this.make = make
  // etc etc
}
```

conventially, constructors start with an Uppercase letter, which is a little different from the usual camelCase

(uh…do I return anything…)

awesome, so the nice thing about making a constructor is now we have a namespace, the “Car” in the Car constructor, we we have all of the properties and methods associated. this makes it easier to organize our code, and as we buid more complex applications we can discuss concepts like Scope that build on putting the code in named blocks like this.

CHECK IN

and now, we can make cars with the Car constructor by using the keyword `new`

`let camry = new Car(blah blah blah)`

We Do: make another car

CHECK IN

now, there’s one last thing we can do to make the Car constructor a little cleaner

when we look at the code, each Car object has the same method, that does the same thing. Why might this be an issue?

(DRY)

so, what we can do is add the method to the Car prototype, and see how that looks like

now, we can use a property on the base Object object, `hasOwnProperty`, to see what’s happeneing here

(ok, that’s pretty good for 15 minutes. I might want to talk briefly about Classes if I have time to spare)