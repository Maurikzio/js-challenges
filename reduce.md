#### sum all the values of an array
````javascript
const sum = [0, 1, 2, 3, 4].reduce((accumulator, currentValue) => {
  return accumulator + currentValue;
}, 0);
console.log(sum); //10
````
#### sum of values in an object array
````javascript
const sum2 = [{x: 1}, {x: 2}, {x: 3}].reduce((accumulator, currentValue) => {
  return accumulator + currentValue.x; //cuidado en poner accumulator.x ->  ya que hay initial value, el initial value no tiene ".x"
},0)
console.log(sum2); //6
```` 

#### flat an array of arrays
````javascript
const flatten = [[0,1], [2, 3], [4, 5]].reduce((accumulator, currentValue) => {
  // accumulator.push(currentValue);
  return accumulator.concat(currentValue);
}, []);
console.log(flatten); //[0 ,1 ,2 ,3 ,4 ,5]
````

#### count instance of value in an object
````javascript
let names = ['Alice', 'Bob', 'Tiff', 'Bruce', 'Alice'];
const countedNames = names.reduce((accumulator, currentValue) => {
  if(currentValue in accumulator){
    accumulator[currentValue]++;
  }else{
    accumulator[currentValue] = 1;
  }
  return accumulator;
},{})
console.log(countedNames); 
/*{
Alice: 2 ,
Bob: 1 ,
Tiff: 1 ,
Bruce: 1
}*/
````

#### remove duplicate items in array
````javascript
let myArray = ['a', 'b', 'a', 'b', 'c', 'e', 'e', 'c', 'd', 'd', 'd', 'd'];
const uniqValues = myArray.reduce((accumulator, currentValue) => {
  if(accumulator.indexOf(currentValue) === -1){
    accumulator.push(currentValue);
  }
  return accumulator;
}, []);
console.log(uniqValues); //["a" ,"b" ,"c" ,"e" ,"d"]
`````

#### grouping objects by  property
````javascript
const people = [
  {name: 'Alice', age: 21},
  {name: 'Max', age: 20},
  {name: 'Jane', age: 20}
];
const byYear = people.reduce((accumulator, currentValue) => {
  const key = currentValue.age; //propiedad por la que queremos ordenar
  if(!accumulator[key]){
    accumulator[key] = [];
  }
  accumulator[key].push(currentValue);
  
  return accumulator;
},{});
console.log(byYear);
/*
{
20: [
  {name: "Max" ,age: 20},
  {name: "Jane" ,age: 20}
  ],
21: [
  {name: "Alice" ,age: 21}
  ]
}*/
`````
#### bonding arrays contained in an array
````javascript
const friends = [
  {name: 'Anna', books: ['Blible', 'Harry Potter'], age: 21},
  {name: 'Bob', books: ['War and peace', 'Romeo and Juliet'], age: 26},
  {name: 'Alice', books: ['The lord of the rings', 'The Shining'], age: 18}
];
const allBooks = friends.reduce((accumulator, currentValue) => {
  return accumulator.concat(...currentValue.books);
}, []);
console.log(allBooks);
//["Blible" ,"Harry Potter" ,"War and peace" ,"Romeo and Juliet" ,"The lord of the rings" ,"The Shining"]
````

#### filter postive numbers and multiply them by 2;
````javascript
const numbers = [-5, 6, 2, 0];
//filter().map() approach
const doublePostiveNumbers = numbers.filter(num => num > 0).map(number => number * 2);
console.log(doublePostiveNumbers); // [12 ,4]

//reduce() approach
const doublePostiveNumbers2 = numbers.reduce((accumulator, currentValue) => {
  if(currentValue > 0){
    accumulator.push(currentValue * 2);
  }
  return accumulator;
},[]);
console.log(doublePostiveNumbers2); // [12 ,4]
````

#### count votes
````javascript
const flavours = [
  "strawberry",
  "strawberry",
  "kiwi",
  "kiwi",
  "kiwi",
  "strawberry",
  "mango",
  "kiwi",
  "banana"
];
const votesOf = (votes, flavor) => {
  return votes.reduce((accumulator, currentValue) => {
    if(currentValue === flavor){
      accumulator++;
    }
    return accumulator
  }, 0);
};
console.log(`strawberry: ${votesOf(flavours, 'strawberry')}`); //strawberry: 3
console.log(`kiwi: ${votesOf(flavours, 'kiwi')}`); //kiwi: 4
console.log(`mango: ${votesOf(flavours, 'mango')}`); //mango: 1
console.log(`banana: ${votesOf(flavours, 'banana')}`); //banana: 1
````

#### turn an array of number into a totall of all numbers
````javascript
function total(arr) {
   return arr.reduce((accumulator, currentValue) => accumulator + currentValue);
}
console.log(total([1,2,3])); // 6
````

#### turn an array of numbers into a long string of all those numbers
````javascript
function stringConcat(arr) {
   return arr.reduce((accumulator, currentValue) => {
     return accumulator + currentValue;
   },"");
}
console.log(stringConcat([1,2,3])); // "123"
````

#### turn an array of voters objects into a count of how many people voted;
````javascript
function totalVotes(arr) {
   return arr.reduce((accumulator, currentValue) => {
      if(currentValue.voted){
        accumulator++;
      }
      return accumulator;
   }, 0);  
}
var voters = [
    {name:'Bob' , age: 30, voted: true},
    {name:'Jake' , age: 32, voted: true},
    {name:'Kate' , age: 25, voted: false},
    {name:'Sam' , age: 20, voted: false},
    {name:'Phil' , age: 21, voted: true},
    {name:'Ed' , age:55, voted:true},
    {name:'Tami' , age: 54, voted:true},
    {name: 'Mary', age: 31, voted: false},
    {name: 'Becky', age: 43, voted: false},
    {name: 'Joey', age: 41, voted: true},
    {name: 'Jeff', age: 30, voted: true},
    {name: 'Zack', age: 19, voted: false}
];
console.log('--3--');
console.log(totalVotes(voters)); // 7
````

#### given an array of all your wishlist, figure out how much it cost to just buy everything at once
````javascript
function shoppingSpree(arr) {
  return arr.reduce((accumulator, currentValue) => {
    return accumulator + currentValue.price;
  },0);   
}

var wishlist = [
    { title: "Tesla Model S", price: 90000 },
    { title: "4 carat diamond ring", price: 45000 },
    { title: "Fancy hacky Sack", price: 5 },
    { title: "Gold fidgit spinner", price: 2000 },
    { title: "A second Tesla Model S", price: 90000 }
];
console.log(shoppingSpree(wishlist)); // 227005
````

#### given a array of arrays, flatten them into a single array
````javascript
function flatten2(arr) {
   return arr.reduce((accumulator, currentValue) => {
    //  return [...accumulator, ...currentValue];
    return accumulator.concat(...currentValue);
   },[]);   
}
var arrays = [
    ["1", "2", "3"],
    [true],
    [4, 5, 6]
];
console.log(flatten2(arrays)); // ["1", "2", "3", true, 4, 5, 6];
````

#### given an array of potential voters, return and object representing the results of the vote
````javascript
//return how many potential voters by ages 18-25,26-35, 36-55
//and how many of each of those ranges voted;
//the result object should have 6 properties
var voters2 = [
    {name:'Bob' , age: 30, voted: true},
    {name:'Jake' , age: 32, voted: true},
    {name:'Kate' , age: 25, voted: false},//y
    {name:'Sam' , age: 20, voted: false},//y
    {name:'Phil' , age: 21, voted: true},//y-1
    {name:'Ed' , age:55, voted:true},
    {name:'Tami' , age: 54, voted:true},
    {name: 'Mary', age: 31, voted: false},
    {name: 'Becky', age: 43, voted: false},
    {name: 'Joey', age: 41, voted: true},
    {name: 'Jeff', age: 30, voted: true},
    {name: 'Zack', age: 19, voted: false}//y
];

function voterResults(arr) {
   return arr.reduce((accumulator, currentValue) => {
      const age = currentValue.age;
      const voted = currentValue.voted
      if(age > 17 && age <26){
        accumulator.youth++
        if(voted){
          accumulator.youngVotes++
        }
      }else if(age>25 && age<36){
        accumulator.mids++;
        if(voted){
          accumulator.midVotes++;
        }
      }else if(age>35 && age<56){
        accumulator.olds++;
        if(voted){
          accumulator.oldVotes++
        }
      }
      return accumulator;
   }, {youngVotes: 0, youth: 0,midVotes: 0, mids:0, oldVotes: 0, olds: 0})
}

console.log(voterResults(voters)); // Returned value shown below:
/*
{ youngVotes: 1,
  youth: 4,
  midVotes: 3,
  mids: 4,
  oldVotes: 3,
  olds: 4 
}
*/
````
