# Javascript-Day-7
12j. Create an arrow function called 'multiply' that takes 2 numbers, multiplies them together, and returns the result.

• multiply(2, 3) => 6

• multiply(7, 10) => 70
```
const multiply = (a,b) => a*b;
      console.log(multiply(2,3));
      console.log(multiply(7,10));
```
12k. Continuing from exercise 12j, write the arrow function on one line (if you already did this, skip this exercise).
```
const multiply = (a,b) => a*b;
      console.log(multiply(2,3));
      console.log(multiply(7,10));
```
121. Create a function countPositive (nums) that takes an array of numbers and returns how many numbers in the array are greater than 0. Create this function using .forEach() instead of a loop.

• countPositive([1, -3, 5]) => 2

• countPositive([-2, 3, 5, 7, 10]) => 3
```

     function countPositive(num){
      let positiveNumber=0;
      num.forEach((num) =>{
        if (num>0)
        positiveNumber++;
      });
      return positiveNumber;
     }
     console.log(countPositive([1,2,3,-5]));
```
m. Create function addNum(array, num) that takes an array of numbers and returns an array where each number is increased by 'num'. Create this function using.map() instead of a loop.

• addNum([1, 2, 3], 2) => [3, 4, 5]

• addNum([-2, -1, 0, 99], 2) => [0, 1, 2, 101]

Bonus: try to use the one-line shortcut in your solution.
```
function addNum(array,num){
      return array.map((value) => value+num);
     };
     console.log(addNum([1,2,3],2));
```
12n. Create a function removeEgg(foods) that takes an array of strings and returns an array where the string 'egg' is removed. Create this function using .filter() instead of a loop.

• removeEgg(['egg', 'apple', 'egg', 'egg', 'ham']) => ['apple', 'ham']
```
function removeEgg(foods){
      let remove=0;
      return foods.filter((foods) => {
        food!=='egg'
     }
     console.log(removeEgg(['egg', 'apple', 'mango', 'egg', 'egg', 'orange','egg']));
```

120. Update exercise 12n to only remove the first 2 eggs from the array. Again, use .filter() instead of a loop.

• removeEgg(['egg', 'apple', 'egg', 'egg', 'ham']) => ['apple', 'egg', 'ham']
```
function removeEgg(foods){
      let remove=0;
      return foods.filter((foods) => {
        if(foods==='egg' && remove<2){
          remove++;
          return false;
        }
        return true;
      });
     }
     console.log(removeEgg(['egg', 'apple', 'mango', 'egg', 'egg', 'orange','egg']));
```
