
#### 1-make an array of numbers that are dounbles of the first array
```javascript
function doubleNumbers(arr){
  return arr.map(number => number*2);
}
console.log(doubleNumbers([2, 5, 100])); //[4, 10, 200]
```
#### 2-take an array of numbers and make them Strings
```javascript
function stringItUp(arr){
  return arr.map(String);
}
console.log(stringItUp([2, 5, 100])); //["2", "5", "100"]
````

#### 3-capitalize each of an array of names
```javascript
function capitalizeNames(arr){
 return arr.map(name => name[0].toUpperCase() + name.slice(1).toLowerCase()); 
}
console.log(capitalizeNames(["john", "JACOB", "jinGleHeimer", "schmidt"])); //["John", "Jacob", "Jingleheimer", "Schmidt"]
````

#### 4 capitalize each word in a certain index
````javascript
var swapCase = function(string){
  return string.split(' ').map((str, index) => {
    return (index % 2 === 0) ? str.toUpperCase() : str;
  });
}
console.log(swapCase('hey gurl, lets javascript together sometime')); //["HEY", "gurl,", "LETS", "javascript", "TOGETHER", "sometime"]
````

#### 5-make an array of strings of the names
````javascript
function namesOnly(arr){
  return arr.map(person => person.name);
}
console.log(namesOnly([
    {
        name: "Angelina Jolie",
        age: 80
    },
    {
        name: "Eric Jones",
        age: 2
    },
    {
        name: "Paris Hilton",
        age: 5
    },
    {
        name: "Kayne West",
        age: 16
    },
    {
        name: "Bob Ziroll",
        age: 100
    }
])); // ["Angelina Jolie", "Eric Jones", "Paris Hilton", "Kayne West", "Bob Ziroll"]
````

#### 6-make an array of strings of the names saying whether or not they ca go to the Matrix; underage or not
```javascript
function makeStrings(arr){
  return arr.map(person => {
     if(person.age<18){
       return `${person.name} is underage`;
     }
      return `${person.name} can go to matrix`;
    });
}
console.log(makeStrings([
    {
        name: "Angelina Jolie",
        age: 80
    },
    {
        name: "Eric Jones",
        age: 2
    },
    {
        name: "Paris Hilton",
        age: 5
    },
    {
        name: "Kayne West",
        age: 16
    },
    {
        name: "Bob Ziroll",
        age: 100
    }
]));  
/*["Angelina Jolie can go to matrix", 
    "Eric Jones is underage", 
    "Paris Hilton is underage", 
    "Kayne West is underage", 
    "Bob Ziroll can go to matrix"]*/
````

#### 7-make an array of the names in h1s and the ages in h2s
````javascript
function readyToPutIntheDOM(arr){
  return arr.map( person => `<h1>${person.name}</h1><h2>${person.age}</h2>`);
}
console.log(readyToPutIntheDOM([
    {
        name: "Angelina Jolie",
        age: 80
    },
    {
        name: "Eric Jones",
        age: 2
    },
    {
        name: "Paris Hilton",
        age: 5
    },
    {
        name: "Kayne West",
        age: 16
    },
    {
        name: "Bob Ziroll",
        age: 100
    }
])); 
/*
["<h1>Angelina Jolie</h1><h2>80</h2>", 
  "<h1>Eric Jones</h1><h2>2</h2>", 
  "<h1>Paris Hilton</h1><h2>5</h2>", 
  "<h1>Kayne West</h1><h2>16</h2>", 
  "<h1>Bob Ziroll</h1><h2>100</h2>"]
*/
````



