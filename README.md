# .forEach, .map, .filter, .reduce, .find

For the following lesson please review [For Loops](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for)!

Why write for loops over and over? they involve way too much writing, they're prone to syntactical errors. 

In the words of Jon Zachary: 

Terser Syntax => less typos => happier developers => world peace

## [.forEach()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)

Call the forEach method on any array, pass it a callback function which invokes three agruments(*Optional*): 
* the element value
* the element index
* the array being traversed

```javascript

const arr = ['a', 'b', 'c', 'd', 'e']

arr.forEach(function(el){
    console.log(el)
})

//expected output
=> 'a'
=> 'b'
=> 'c'
=> 'd'
=> 'e'

arr.forEach((d, i, a) => {
    console.log(`this is ${d}, this is the index ${i}, this is the array being traversed: ${a}`)
})

//expected output
=> "this is a, this is the index 0, this is the array being traversed: a,b,c,d,e"
=> "this is b, this is the index 1, this is the array being traversed: a,b,c,d,e"
=> "this is c, this is the index 2, this is the array being traversed: a,b,c,d,e"
=> "this is d, this is the index 3, this is the array being traversed: a,b,c,d,e"
=> "this is e, this is the index 4, this is the array being traversed: a,b,c,d,e"

```

##[.map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)

Use the `.map()` method on any array, it will return a new array with new mutated values. 

```javascript

let arr = [1, 2, 3, 4, 5]

const mapped = arr.map( d => d * 2 ); 

console.log(mapped)

//expected output:

=> [2, 4, 6, 8, 10]

```

## [.filter()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)

This method creates a new array with all the elements that pass the test implemented by the function... or it FILTERS everything you're not looking for. 

```javascript

let names = ["Carlos", "Dmitriy", "Angel", "Ester", "Alberto", "Magnardo"]

const filtered = names.filter( name => name.length > 5); 

console.log(filtered)

//expected output: 

["Carlos", "Dmitriy", "Alberto", "Magnardo"]

```
## [.reduce()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)
The `reduce()` method executes a reducer function (that you provide) on each memeber of the array against an accumulator and each element in the array (from left to right) to be *REDUCED* to a single value

```javascript
let arr = [1, 2, 3, 4, 5, 6, 7]; 
let reducer = (accumulator, value) => {
    return accumulator + value; 
}
let newArr = arr.reduce(reducer)

//expected output
=> 28
```


## [.find()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find)

Use the `.find()` method on any array and it returns the **value** of the **first element** in the arrat that satisfies the callback function, otherwise `undefined` is returned. Just like the .forEach() method, the callback function also can take three arguments. 

```javascript

const arr = [5, 6, 30, 35, 90, 130,  9]; 

let found = arr.find((d) => {
    return d > 30; 
});

console.log(found); 

//expected output
=> 35

```