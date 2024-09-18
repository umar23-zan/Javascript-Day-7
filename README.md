# Javascript-Day-7
j. Create an arrow function called 'multiply' that takes 2 numbers, multiplies them together, and returns the result.

• multiply(2, 3) => 6

• multiply(7, 10) => 70
```
const multiply = (a,b) => a*b;
      console.log(multiply(2,3));
      console.log(multiply(7,10));
```
k. Continuing from exercise 12j, write the arrow function on one line (if you already did this, skip this exercise).
```
const multiply = (a,b) => a*b;
      console.log(multiply(2,3));
      console.log(multiply(7,10));
```
1. Create a function countPositive (nums) that takes an array of numbers and returns how many numbers in the array are greater than 0. Create this function using .forEach() instead of a loop.

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
n. Create a function removeEgg(foods) that takes an array of strings and returns an array where the string 'egg' is removed. Create this function using .filter() instead of a loop.

• removeEgg(['egg', 'apple', 'egg', 'egg', 'ham']) => ['apple', 'ham']
```
function removeEgg(foods){
      let remove=0;
      return foods.filter((foods) => {
        food!=='egg'
     }
     console.log(removeEgg(['egg', 'apple', 'mango', 'egg', 'egg', 'orange','egg']));
```

0. Update exercise 12n to only remove the first 2 eggs from the array. Again, use .filter() instead of a loop.

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
12p. Go back to the earlier exercises in lesson 12 (12c - 12i) and switch the code to use arrow functions. (When passing a function into another function, use arrow functions. Otherwise, you can use either syntax.)
```
<button class="js-button" onclick="
      updateButton();
    ">Start</button>

    <script>
      function updateButton() {
        const button = document.querySelector('.js-button');
        setTimeout(() => {
          button.innerHTML = 'Finished!';
        }, 1000);
      }
```
12q. Go back to the earlier exercises in lesson 12 (12c-12i) and instead of using onclick="...", switch the code to use.addEventListener('click', ...)

Challenge Exercises

The following exercises will build on the Rock Paper Scissors game.
```
<button class="js-button">Start</button>

<script>
document.querySelector('.js-button')
  .addEventListener('click', () => {
    const button = document.querySelector('.js-button');
    setTimeout(() => {
      button.innerHTML = 'Finished!';
    }, 1000);
  });
```
12r. Make a copy of the Rock Paper Scissors game into the files 12r.html, 12r.css, and 12r.js.

• Update the <link> and <script> elements to load 12r.css and 12r.js. • Also, make a copy of the images and make sure they load properly.
```
<!DOCTYPE html>
<html>
  <head>
    <title>Rock Paper Scissors</title>
    <link rel="stylesheet" href="12r.css">
  </head>
  <body>
    <p class="title">Rock Paper Scissors</p>
    <button class="move-button js-rock-button">
      <img src="images/rock-emoji.png" class="move-icon">
    </button>

    <button class="move-button js-paper-button">
      <img src="images/paper-emoji.png" class="move-icon">
    </button>

    <button class="move-button js-scissors-button">
      <img src="images/scissors-emoji.png" class="move-icon">
    </button>

    <p class="js-result result"></p>
    <p class="js-moves"></p>
    <p class="js-score score"></p>

    <!-- Solution for exercise 12v. -->
    <button class="reset-score-button js-reset-score-button">
      Reset Score
    </button>

    <!-- Solution for exercise 12s. -->
    <button class="auto-play-button js-auto-play-button">
      Auto Play
    </button>

    <!-- Solution for exercise 12x. -->
    <p class="js-reset-confirmation"></p>
    
    <script src="12r.js"></script>
  </body>
</html>
```
12s. Update the 'Auto Play' button to use.addEventListener('click', ...) instead of onclick="..."
```
<button class="auto-play-button js-auto-play-button">
  Auto Play
</button>

document.querySelector('.js-auto-play-button')
  .addEventListener('click', () => {
    autoPlay();
  });
```
12t. Update the 'Auto Play' button so that when the game is auto playing, the text in the button is 'Stop Playing'. Otherwise, the text in thebutton is 'Auto Play'.
```
function autoPlay() {
  if (!isAutoPlaying) {
    intervalId = setInterval(() => {
      const playerMove = pickComputerMove();
      playGame(playerMove);
    }, 1000);
    isAutoPlaying = true;
    
    
    document.querySelector('.js-auto-play-button')
      .innerHTML = 'Stop Playing';

  } else {
    clearInterval(intervalId);
    isAutoPlaying = false;

    
    document.querySelector('.js-auto-play-button')
      .innerHTML = 'Auto Play';
  }
}
```
12u. Update the code so pressing 'a' on keyboard will auto play the game.
```
document.body.addEventListener('keydown', (event) => {
  if (event.key === 'r') {
    playGame('rock');
  } else if (event.key === 'p') {
    playGame('paper');
  } else if (event.key === 's') {
    playGame('scissors');
  
  } else if (event.key === 'a') {
    autoPlay();
  }
});
```
12v. Update the 'Reset Score' button to use .addEventListener('click', ...)
```
<button class="reset-score-button js-reset-score-button">
  Reset Score
</button>
<script>
function resetScore() {
  score.wins = 0;
  score.losses = 0;
  score.ties = 0;
  localStorage.removeItem('score');
  updateScoreElement();
}
document.querySelector('.js-reset-score-button')
  .addEventListener('click', () => {
    resetScore();
  });
</script>
```
12w. Update the code so pressing 'Backspace' will reset the score.
```
document.body.addEventListener('keydown', (event) => {
  if (event.key === 'r') {
    playGame('rock');
  } else if (event.key === 'p') {
    playGame('paper');
  } else if (event.key === 's') {
    playGame('scissors');
  } else if (event.key === 'a') {
    autoPlay();
  
  } else if (event.key === 'Backspace') {
    resetScore();
  }
});
```
12x. When clicking 'Reset Score' or pressing 'Backspace', instead of resetting the score immediately, display a confirmation message below the button:

Are you sure you want to reset the score?

Yes

No

1528

• Clicking 'Yes' will reset the score, and hide the message.

• Clicking 'No' will not reset the score, and hide the message.
```
<p class="js-reset-confirmation"></p>
<script>
document.querySelector('.js-reset-score-button')
  .addEventListener('click', () => {
    showResetConfirmation();
  });

function showResetConfirmation() {
  document.querySelector('.js-reset-confirmation')
    .innerHTML = `
      Are you sure you want to reset the score?
      <button class="js-reset-confirm-yes reset-confirm-button">
        Yes
      </button>
      <button class="js-reset-confirm-no reset-confirm-button">
        No
      </button>
    `;
  
  document.querySelector('.js-reset-confirm-yes')
    .addEventListener('click', () => {
      resetScore();
      hideResetConfirmation();
    });
  
  document.querySelector('.js-reset-confirm-no')
    .addEventListener('click', () => {
      hideResetConfirmation();
    });
}
function hideResetConfirmation() {
  document.querySelector('.js-reset-confirmation')
    .innerHTML = '';
}
</script>
```

## Amazon project
13a. The HTML element for a dropdown selector is <select>. Use Ctrl + F or Cmd + F to find this in the code (in amazon.js).
```
open amazon.js
use ctrl+f
type "select"
```
13b. When generating the HTML, add a unique class to <select> to identify which product the dropdown is for (class="js-quantity-selector-${product.id})")
```
<select class="js-quantity-selector-${product.id}">
```
13c. When clicking the 'Add to Cart' button, use the DOM to get the quantity selector (the <select> element) for the product. Hint: use document.querySelector(.js-quantity-selector-${productid})
```
const quantitySelector=document.querySelector(`.js-quantity-selector-${productid}`);
```
13d. Get the value selected in the quantity selector (to get the value out of a <select> element, you can use the property '.value')
```
const quantity = quantitySelector.value;
```
13e. When updating the cart, instead of using a quantity of 1 every time, use the quantity that we got from 13d. Hint: in order for the math to work properly, convert the value from 13d into a number first using Number() (since values we get from the DOM are strings by default).
```
const quantity = Number(quantitySelector.value);

      if (matchingItem) {
        matchingItem.quantity += quantity;
      } else {
        cart.push({
          productId: productId,
          quantity: quantity
        });
      }
```
13f. Select a quantity other than 1 and click 'Add to Cart'. The quantity selector should now work. Check the changes for 13a - 13e in Git and commit the changes.
```
const quantitySelector=document.querySelector(`.js-quantity-selector-${productid}`);

      const quantity = Number(quantitySelector.value);

      if (matchingItem) {
        matchingItem.quantity += quantity;
      } else {
        cart.push({
          productId: productId,
          quantity: quantity
        });
      }
```
13g. We'll add some more products to the page. Inside data/products.js add some more objects to the array. For the id, use any id that you want, like 'id', 'id2', etc. (just make sure its unique). For the image, I've provided "images/products/backpack.jpg" and "images/products/umbrella.jpg" or find an image yourself online. For the name, rating, and priceCents, use any values that you want.
```
{
    id: "id1",
    image: "images/products/backpack.jpg",
    name: "Black Backpack",
    rating: {
      stars: 4.5,
      count: 123
    },
    priceCents: 2500
  },
  {
    id: "id2",
    image: "images/products/umbrella.jpg",
    name: "Large Green Umbrella",
    rating: {
      stars: 5,
      count: 456
    },
    priceCents: 2999
  }
```
13h. We'll review some JavaScript shortcuts we can use. In amazon.js:
Search for the code 'const productId = button.dataset.productid;' and use the destructuring shortcut to simplify it. Search for 'cart.push({' and use shorthand property in the 2 lines
```
const {productId} = button.dataset;
productId,
quantity
```
Challenge Exercises

We'll create the 'Added' message on the right. The HTML element for this already exists: <div class="added-to-cart"> However, in the CSS, this element has opacity: 0 (it's invisible).

13i. Add a unique class to this element (like we did in exercise 13b) to identify which product it is for.
```
<div class="added-to-cart js-added-to-cart-${product.id}">
```
13j. When clicking 'Add to Cart', use the DOM to get the 'Added' message element for the product (like we did in exercise 13c).
```
const addedMessage = document.querySelector(
        `.js-added-to-cart-${productId}`
      );
```
13k. Add a class to the message element using.classList.add(). Then, in styles/pages/amazon.css, style this class so it has opacity: 1;
```
 addedMessage.classList.add('added-to-cart-visible');

.added-to-cart-visible {
  opacity: 1;
```
13m. If we click 'Add to Cart', wait 1 to 1.5 seconds, and click again, the message disappears quickly (since the previous setTimeout is still running and will make the message disappear soon).

• Modify the code so when we click 'Add to Cart', it "refreshes" the 2 second wait time (waits 2 seconds again and message disappears)

• Hint: you can cancel the previous setTimeout using clearTimeout()

Incorrect X

Correct

```
 let addedMessageTimeoutId;

    button.addEventListener('click', () => {
      const {productId} = button.dataset;



      addedMessage.classList.add('added-to-cart-visible');

      setTimeout(() => {
      
      if (addedMessageTimeoutId) {
        clearTimeout(addedMessageTimeoutId);
      }

      const timeoutId = setTimeout(() => {
        addedMessage.classList.remove('added-to-cart-visible');
      }, 2000);

     
      addedMessageTimeoutId = timeoutId;
```
