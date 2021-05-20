# array-methods

### map - Creates a new array with new data from an existing array.
```javascript
const numArr = [1, 2, 3]

const map1 = numArr.map( x => x + 1)
// map1 = [2, 3, 4]

const map2 = numArr.map( x => x * 2)
// map2 = [2, 4, 6]

const map3 = numArr.map( x => x + 'a')
// map3 = ['1a', '2a', '3a']
```

### reduce - Returns a single value from data of an existing array.
```javascript
const numArr = [1, 2, 3, 4, 5]

numArr.reduce( (total, current) => total + current, 0)
// 15

numArr.reduce( (total, current) => total - current, 0)
// -15

numArr.reduce( (total, current) => total * current, 1)
// 120
```
### filter - Creates a new array of values that passes a test given by a function.
```javascript
const numArr = [1, 2, 3, 4, 5, 6, 7, 8, 9]

numArr.filter( num => num % 2 === 0) 
// [2, 4, 6, 8]

numArr.filter( num => num % 2 !== 0)
// [1, 3, 5, 7, 9]

numArr.filter( num => num <= 5) 
// [1, 2, 3, 4, 5]
```

### forEach - Does one thing to each value by a given function.
```javascript
const numArr = [1, 2, 3, 4, 5]

numArr.forEach( num => num + 1)
// [2, 3, 4, 5, 6]

numArr.forEach( num => num * 5)
// [5, 10, 15, 20, 25]

numArr.forEach( num => num - 2)
// [-1, 0, 1, 2, 3]
```

### sort - Rearranges values of a given array based on restrictions.
```javascript
const fruits = ['bananas', 'apples', 'oranges', 'grapes']
fruits.sort() // ['apples', 'bananas', 'grapes', 'oranges']

const numArr = [345, 12, 67, 3423, 910]
numArr.sort() // [12, 3423, 345, 67, 910]

const numArr = [345, 12, 67, 3423, 910]
numArr.sort( (a, b) => a - b ) // [12, 67, 345, 910, 3423] (lowest to highest value)
```

### slice - Makes an array shorter in length by removing one or some of its values. Can take 2 values .slice(x,y). x will be included in the new array, up to y (excluding y)
```javascript
const numArr = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

numArr.slice(1)
// [1, 2, 3, 4, 5, 6, 7, 8, 9]

numArr.slice(2, 5)
// [2, 3, 4]

numArr.slice(-5)
// [5, 6, 7, 8, 9]
```

### pop - Removes last element from array. Output will be that element.
```javascript
const fruits = ['apples', 'bananas', 'grapes', 'oranges', 'blueberries']

console.log(fruits.pop()) // 'blueberries'

console.log(fruits) // ['apples', 'bananas', 'grapes', 'oranges']

fruits.pop() 'oranges'
console.log(fruits) // ['apples', 'bananas', 'grapes']
```

### shift - Removes first element from array. Output will be that element.
```javascript
const fruits = ['apples', 'bananas', 'grapes', 'oranges', 'blueberries']

console.log(fruits.shift()) // 'apples'

console.log(fruits) // ['bananas', 'grapes', 'oranges', 'blueberries']

fruits.shift() // 'bananas'
console.log(fruits) // ['grapes', 'oranges', 'blueberries']

```

### push - Adds one or more elements to the end of an array. 
```javascript
const fruits = ['apples', 'bananas']

fruits.push('oranges')
console.log(fruits) // ['apples', 'bananas', 'oranges']

fruits.push('grapes', 'blueberries')
console.log(fruits) // ['apples', 'bananas', oranges', 'grapes', 'blueberries']
```

### unshift - Adds one or more elements to the beginning of an array.
```javascript
const fruits = ['apples', 'bananas']

fruits.unshift('oranges')
console.log(fruits) // ['oranges', 'apples', 'bananas']

fruits.unshift('grapes', 'blueberries')
console.log(fruits) // ['grapes', 'blueberries', 'oranges', 'apples', 'bananas']
```

### includes - Determines if an array contains a certain value. Returns a boolean.
```javascript
const numArr = [1, 2, 3]
console.log(numArr.includes(1))
// true

const fruits = ['apples', 'oranges', 'bananas']
console.log(fruits.includes('apples'))
// true
console.log(fruits.includes('pineapples'))
// false
```

### indexOf - Returns the element at the provided index of an array.
```javascript
const fruits = ['apple', 'bananas', 9034, 'oranges']

console.log(fruits.indexOf(0))
// 'apple'

console.log(fruits.indexOf(2))
// 9034

console.log(fruits.indexOf(3))
// 'oranges'
```

### every - Determines if all elements passes a test given by a function. Returns a boolean.
```javascript
const isPositive = num => num > 0

const numArr1 = [1, 2, 3, 4, 5]
console.log(numArr1.every(isPositive))
// true

const numArr2 = [1, 2, -3, 4, 5]
console.log(numArr2.every(isPositive))
// false

const mixedArr = ['a', 'b', 'c', 3]
console.log(mixedArr.every(isPositive))
// false
```
## Practice Questions 
 
### Given a non-empty array of integers, return the result of multiplying the values together in order. Example: [1, 2, 3, 4] => 1 * 2 * 3 * 4 = 24 

```javascript
[1, 2, 3, 4].reduce( (total, current) => total * current, 1)
```

### You will be given an array of all the family members' ages, in any order. The ages will be given in whole numbers, so a baby of 5 months, will have an ascribed 'age' of 0. Return a new array with [youngest age, oldest age, difference between the youngest and oldest age]. 

```javascript
const newArr = []

familyAges.sort( (a, b) => a - b) // sorts family ages from lowest to highest
newArr.push(familyAges[0]) // adds first element of familyAges to newArr
newArr.push(familyAges[familyAges.length - 1] // adds last element of familyAges to newArr

const difference = newArr.reverse().reduce( total, current) => total - current, 0) // Subtracts both numbers in newArr to get difference
newArr.push(difference) // adds difference to newArr

return newArr
```
 
### Sum all the numbers of the array except the highest and the lowest element (the value, not the index!). Example: [ 6, 2, 1, 8, 10 ] => 16 [ 1, 1, 11, 2, 3 ] => 6
```javascript
numArr.sort( (a, b) => a - b) // sorts numbers from lowest to highest
numArr.slice(1, numArr.length) // removes first and last number
numArr.reduce( (total, current) => total + current, 0) // sums remaining numbers
```
