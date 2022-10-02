# Objects in Javascript 

## Primitive Types
<p>
There are 7 primitive types in JavaScript: 

1. String -> <i> "Hello" "5" "🍟"</i>
2. Number -> <i> 5 , 4 , 4000, etc.</i>
3. Boolean -> <i> True or False values </i>
4. Undefined -> <i> value given to a variable when it's value is unknown. It can be read as "this variable has not been given a value yet"</i>
5. Null -> <i> value given to a variable when it's value is nothing. It usually can be read as "this variable has been given the value of nothing" </i>
6. Symbol -> <i> const type = Symbol('crypto')</i>
7. Bigint -> <i> const someHugeNumber = 9007199254740994n; </i>
</p>

## Objects 

<p>
Everything in JavaScript that is not primitive is an object. 

* Objects contain data and functionality that works on the contained data. 
* Objects are made up of key-value pairs. The object stores a value at a <b> key</b>. 
* <b>Key</b> should (almost always) be strings - they can technically be any primitive.

Everything in JavaScript is either a primitive or an object - thus arrays and functions are Objects. 
</p>

### Object Declaration Syntax 
``` js  
const instructor = {
  name: 'Ian B',
  location: 'Montral, QC',
  isEnrolled: true,
  age: 34,
  plants: ['pothos', 'corn', 'aloe', 'fiddle head fig', 'asparagus fern']
};

// to access value either
// 1. square bracket notation
console.log(instructor['name']); // > Ian B

// 2. dot notation
console.log(instructor.name); // > Ian B  

```

If the key of the object is known, use dot notation otherwise use bracket notation. 

``` js
const keyToLookup = 'name';
console.log(instructor[keyToLookup]);
```

## Primitives are Passed as values 
When you pass a primitive type to a function, it is passed as a value: a copy is passed and the original primitive is unchanged. 

``` js
let instructor = 'Ian';

const updateInstructor = function(instructor){
  instructor = 'Taiwo';
  console.log('instructor during function:', instructor)
}

console.log(instructor) // > Ian
console.log(updateInstructor(instructor)) // > Taiwo
console.log(instructor) // > Ian
```
<b> Remember the rule primitives are passed by values.

Changes made to primitives inside of functions do not persist.</b>

## Objects are Passed as References 

When you pass an object to a function, then a reference to the object is passed. Changes made to an object will modify the original. 

``` js 
const instructor = {
  name: 'Ian B',
  location: 'Montral, QC'
};

const updateInstructor = function(instructor){
  instructor.name = 'Taiwo O';
  console.log('instructor name during function:', instructor.name);
}

console.log("instructor name before function:", instructor.name) // > Ian
console.log(updateInstructor(instructor)) // > Taiwo
console.log("instructor name after function:", instructor.name) // > Taiwo
```
<b> Remember the rule of objects are passed by reference. 

Changes made to objects inside of functions do effect the original!
</b>

**See the difference in pythontutor

## Methods & Context

Functions inside objects are known as methods and can be called much like accessing other values inside objects.

In order to access other attributes of the object, within the <i> "context" </i> of the function, use the <b>this</b> keyword.

``` js
 const car = {
  name: 'Camry',
  brand: 'Toyota',
  mileage: 10_000,
  fuelLevel: 18,
  maxFuelLevel: 30,
  litrePerKm: 0.05,
  drive: function (km) {
      this.mileage += km;
      this.fuelLevel -= (km * this.litrePerKm);
  }
};

console.log(car.fuelLevel);
car.drive(100);
console.log(car.fuelLevel);

// function expression then assign to an object key
const refuel = function() {
  const amountOfFuel = this.maxFuelLevel - this.fuelLevel;
  return amountOfFuel;
}
car.refuel = refuel;

console.log(car.fuelLevel);
console.log(car.refuel());
```
Note: Context is a very subtle idea in JavaScript, and later in the program we will spend more time dedicated to understanding the nuances of it's usage and application. 

## Looping Objects and Arrays 

As we saw last time, we use ``` "for ... of"``` to loop over an array. 

``` js
const destinations = ['Vancouver', 'Calgary', 'Edmonton', 'Saskatoon', 'Regina'];

for (const destination of destinations) {
    console.log("Now arriving", destination);
}
```
Remember ```for ... of``` loops are designed for arrays!

With objects, we use ```for ... in``` to iterate over the ```keys``` of the object. 

```js
const instructors = {
  1: {
      id: '1',
      name: 'Ian'
  },
  2: {
      id: '2',
      name: 'Taiwo'
  }
};

for (const key in instructors) {
  // key is variable, so use bracket notation to access the value
  console.log(key, instructors[key])
}
/*
>
1 { id: '1', name: 'Ian' }
2 { id: '2', name: 'Taiwo' }
*/
```
Remember ```for ... in``` loops are designed for objects!

## Resources:
* [Code Repo](https://github.com/idbentley/lighthouse-lectures/tree/main/flex-w2d1-full-w1d3-objects-js)
* [Video - 1](https://vimeo.com/672510780/dea0f13ebe)
* [Video - 2](https://vimeo.com/754543278/95d58034e9)

## Links:
* [MDN: Object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
* [Dot Notation vs Square Brackets](https://codeburst.io/javascript-quickie-dot-notation-vs-bracket-notation-333641c0f781)
* [Python Tutor](http://www.pythontutor.com/javascript.html#mode=edit)
* [Symbol Type](https://javascript.info/symbol)
* [The Essential Guide to JavaScript's Newest Data Type: BigInt](https://www.smashingmagazine.com/2019/07/essential-guide-javascript-newest-data-type-bigint/)

### [Back to main page](../README.md)
