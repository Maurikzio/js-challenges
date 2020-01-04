## Home
### Non-unique Elements
code
```javascript
    function nonUniqueElements(data) {
        return data.filter(element => data.indexOf(element) !== data.lastIndexOf(element));
    }
```
test
```javascript
nonUniqueElements([1, 2, 3, 1, 3]) == [1, 3, 1, 3]
nonUniqueElements([1, 2, 3, 4, 5]) == []
nonUniqueElements([5, 5, 5, 5, 5]) == [5, 5, 5, 5, 5]
nonUniqueElements([10, 9, 10, 10, 9, 8]) == [10, 9, 10, 10, 9]
```

### Median
code
```javascript
    function median(data) {
        let arr = data.sort((a, b) => a - b);
        let med = 0;
        if(arr.length % 2 === 0){
            //even
            med = arr.splice(arr.length/2-1, 2)
                     .reduce((sum, current) => (sum + current) / 2);
        }else{
            //odd
            med = arr[Math.floor(arr.length/2)];
        }
        return med;
    }
```
test
```javascript
    median([1, 2, 3, 4, 5]) == 3
    median([3, 1, 2, 5, 3]) == 3
    median([1, 300, 2, 200, 1]) == 2
    median([3, 6, 20, 99, 10, 15]) == 12.5
```

### The Most Wanted Letter
code
```javascript
    function numberOfOcurrences(str, char){
        let reps = 0;
        let pos = 0;
        while( true ){
            let targetPos = str.indexOf(char, pos);
            if(targetPos == -1 ) break;
            reps += 1;
            pos = targetPos + 1;
        }
        return reps;
    }

    function mostWanted(data){
        data = data.replace(/[^a-z]+/gi, '').toLowerCase().split("").sort().join("");
        let most = data[0];
        let reps = numberOfOcurrences(data, most);
        for( let i = 1; i<data.length; i++){
            if( numberOfOcurrences(data, data[i]) > reps) {
                most = data[i];
                reps = numberOfOcurrences(data, data[i]);
            }
        }
        return most;
    }
```


test
```javascript
    mostWanted("Hello World!") == "l"
    mostWanted("How do you do?") == "o"
    mostWanted("One") == "e"
    mostWanted("Oops!") == "o"
    mostWanted("AAaooo!!!!") == "a"
    mostWanted("abe") == "a"
```

### Long Repeat
code
```javascript
    function longRepeat(line) {
        // length the longest substring that consists of the same char
        let longest = 1;
        let current = 1;
        let arr = line.split("");

        if(!line) return 0; 

        for( let i=1; i<arr.length; i++) {
            if(arr[i] === arr[i-1]){
                current += 1;
            }else{
                current = 1;
            }
            longest = Math.max(longest, current);
        }
        return(longest);
    }
```


test
```javascript
longRepeat('sdsffffse') == 4
longRepeat('ddvvrwwwrggg') == 3
```
