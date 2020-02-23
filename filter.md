#### filter even numbers
````javascript
const numbers = [1, 5, 7, 10];
function isEven(number) {
  return number % 2 === 0;
}
const evens = numbers.filter(isEven);
console.log(evens); //[10]

//2
function evensOnly(arr) {
  return arr.filter(number => number%2===0);
}
// test
console.log(evensOnly([3, 6, 8, 2])); /// [6, 8, 2]
````
#### filter elements with values less than 10
````javascript
const isBigEnough = value => {
  return value >= 10;
};
const filtered = [12, 5, 8, 130, 44].filter(isBigEnough);
console.log(filtered); //[12 ,130 ,44]
````
#### find all prime numbers in array
````javascript
const array = [4, 6, 8, 9, 12, 53, -17, 2, 5, 7, 31, 97, -1, 17];
const isPrime = number =>{
  if(number <= 1) {
    return false;
  }
  for(let i=2; i<number; i++){
    if(number%i === 0)
    return false
  }
  return true;
};
const primes = array.filter(isPrime);
console.log(primes); //(7) [53 ,2 ,5 ,7 ,31 ,97 ,17]
`````
#### searching in array
````javascript
const fruits = ['apple', 'banana', 'grapes', 'mango', 'orange'];
function filterItems(arr, query){
  return arr.filter(function(value){
    return value.toLowerCase().indexOf(query.toLowerCase()) !== -1;
  });
}
//ES6
// const filterItems = (arr, query) => {
//   return arr.filter(el => el.toLowerCase().indexOf(query.toLowerCase()) !== -1);
// }
console.log(filterItems(fruits, 'ap')); // ["apple" ,"grapes"]
console.log(filterItems(fruits, 'an')); //["banana" ,"mango" ,"orange"]
````
#### given an array of numbers, reurn a new array that has only the numbers that are 5 or greater
````javascript
function fiveAndGreaterOnly(arr) {
  return arr.filter(value => value >= 5);
}
// test
console.log(fiveAndGreaterOnly([3, 6, 8, 2])); /// [6, 8]
````
#### given an array of strings, return a new array that only includes those that are 5 characters or fewer in length
````javascript
function fiveCharactersOrFewerOnly(arr) {
  return arr.filter(word => word.length < 6);
}
// test
console.log(fiveCharactersOrFewerOnly(["dog", "wolf", "by", "family", "eaten", "camping"])); // ["by", "dog", "wolf", "eaten"]
````
#### given an arrya of people objects, return a new array that has filtered out all those who dont belong to the club
````javascript
function peopleWhoBelongToTheIlluminati(arr){
  return arr.filter(person => person.member);
}
// test
console.log(peopleWhoBelongToTheIlluminati([
    { name: "Angelina Jolie", member: true },
    { name: "Eric Jones", member: false },
    { name: "Paris Hilton", member: true },
    { name: "Kayne West", member: false },
    { name: "Bob Ziroll", member: true }
]));
// =>
//[ { name: 'Angelina Jolie', member: true },
//  { name: 'Paris Hilton', member: true },
//  { name: 'Bob Ziroll', member: true } ]
````

#### make a filtered list of all the people who are old enough to see The Matrix(younger than 18)
````javascript
function ofAge(arr){
  return arr.filter(person => person.age > 18);
}
// test
console.log(ofAge([
    { name: "Angelina Jolie", age: 80 },
    { name: "Eric Jones", age: 2 },
    { name: "Paris Hilton", age: 5 },
    { name: "Kayne West", age: 16 },
    { name: "Bob Ziroll", age: 100 }
])); 
// => 
//[ { name: 'Angelina Jolie', age: 80 },
//  { name: 'Bob Ziroll', age: 100 } ]
````


