# 100DEVS BACKEND SUPER REVIEW
Source: [LearnWithLeon - Backend Super Review](https://slides.com/leonnoel/backend-crash-course-100devs-2#/76)

**What is a Program?**
A program is a set of instructions that you write to tell a computer what to do
What is a programming?
Programming is the task of writing those instructions in a language that the computer can understand.
Simple Circut

**Variables**
- Declaration: `let age`
- Assignment: `age = 25`
- Both: `let age = 25`

**Conditional Syntax**
```
if (condition is true) {
    // do stuff
}
```

```
if(condition is true) {
  //Do this cool stuff
}else if(condition is true){
  //Do this other cool stuff
}else{
  //Default cool stuff
}
```

# Functions
- Functions are simple sets of instructions!
- Functions are reusable
- Functions perform one action as a best practice
- They form the basic "building blocks" of a program

# Loops
- Repeat an action some number of times!
- Three main types of loops in Javascript
- For, while, and do while loops
- Each type offers a different way to determine the start and end points of a loop

## Loops - For
```
for (let i = 1; i < 5; i++) {
  console.log(i)
}
```

# Arrays
- A data structure to store ordered collections!
- Array elements are numbered starting with zero
- Arrays have many methods to manage the order of elements
- Can be created by a constructor or literal notation


## Declaring Arrays
Literal notation: `let newArr = []`

## Array Indexing
Elements can be updated by using the index of that position

```
newArr = ['Zebra',,true,21]

console.log( newArr[0] )  //Zebra
console.log( newArr[1] )  //undefined
console.log( newArr[2] )  //true
console.log( newArr[3] )  //21
```

# Objects
- Objects are a collection of variables and functions!
- Objects represent the attributes and behavior of something used in a program
- Object variables are called properties and object functions are called methods
- Objects store "keyed" collections

```
let stopwatch = {}

stopwatch.currentTime = 12

stopwatch.tellTime = function(time){
  console.log(`The current time is ${time}.`)
}

stopwatch.tellTime(stopwatch.currentTime)
```

## New Syntax
```
class MakeCar{
  constructor(carMake,carModel,carColor,numOfDoors){
    this.make = carMake
    this.model = carModel
    this.color = carColor
    this.doors = numOfDoors
  }
  honk(){
    alert('BEEP BEEP')
  }
  lock(){
    alert(`Locked ${this.doors} doors!`)
  }
}

let hondaCivic = new MakeCar('Honda','Civic','Silver', 4)

let teslaRoadster = new MakeCar('Tesla','Roadster', 'Red', 2)
```
# APIs
- A simple interface for some complex action!
- Think of a restaurant menu! Remember those...
- Lets one thing communicate with another thing without having to know how things are implemented.

![](https://media.slid.es/uploads/549074/images/7783759/api.png)

- API returns a JSON object taht we can use within our apps
```
fetch("https://dog.ceo/api/breeds/image/random") // returns a promise
    .then(res => res.json()) // if you get a response, parse response as JSON
    .then(data => {
      console.log(data)
    })
    .catch(err => {
        console.log(`error ${err}`)
    });
```

# JavaScript
- JavaScript is single-threaded
- Synchronous aka processes one operation at a time

## The Environment
If synchronous, how do we do stuff like make an api request and keep scrolling or clicking

**JavaScript is running in a browser**
- Browsers have a BUNCH of APIs we can use that are async and enable us to keeping looking a cute cat photos while those operations are being processed asynchronously
- JavaScript can do a lot of blocking in the browser because it is handing that data off to async Web APIs
- JavaScript handles responses coming back from Web APIs with callbacks, promises, and async/await
- Higher Order Function: You can have a function that takes another function as an argument
`addEventListener('click', callback)`

### Callback
**Callback:** the function that has been passed as an argument
- Callback fires when async task or another function is done
```
function houseOne(){
    setTimeout(() => {
        console.log('Paper delivered to house 1')
        setTimeout(() => {
            console.log('Paper delivered to house 2')
            setTimeout(() => {
                console.log('Paper delivered to house 3')
            }, 3000)
        }, 4000)
    }, 5000)
}
houseOne()
```
### Promise
**Promise:** An object that MAY have a value in the future

`.then()`: A promise object method that runs after the promise "resolves"

`.then(value)`: Whatever value the promise object has gets passed as an argument
```
fetch("https://dog.ceo/api/breeds/image/random")
    .then(res => res.json()) // parse response as JSON
    .then(data => {
      console.log(data)
    })
    .catch(err => {
        console.log(`error ${err}`)
    });
```
**Fetch returns a Promise**

> `res` is a Response object - containing info about the response from status code, headers, and what we want, the unprocessed body of the request. Then we call and return res.json(), which both reads/consumes the body of the request and parses it as JSON, returning whatever was JSON-ified - which is usually an object

> So there's a link button with a click event listener, so when you click a fetch() is made to tell the backend server to mark the post as liked. Then, we get the response, return the json of the resonse, and then if the liking was successful, update the number of likes in the DOM 
