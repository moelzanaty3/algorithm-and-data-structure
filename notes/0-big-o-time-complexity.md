# Big O Time Complexity

Hi there 👋, in this note, we will talk about Big O Notation, what is it? why we need it? and how to use it?

Simply let's start with what's Big O Notation?

In simple words, it is a metric for determining an algorithm's efficiency. It's a way to compare how fast an algorithm is, it gives an estimate of how long it takes your code to run on different sets of inputs. Also known as the algorithm's upper bound since it analyses the worst-case situation.

> Imagine you're playing a game. Sometimes, things go perfectly from the start, and you finish quickly. That's like the best way things can happen! But there are times when things get really tricky, and it's harder to finish the game. We think about these tricky times because they help us make sure we're always doing at least as well as the hardest part. It's like knowing we'll always do our best or even better than the hardest part of the game!

but Are we really need to care about Big O?

- Yes, because it's important to know how long your code will take to run.
- It's important to know how much memory your code will take up.
- It's important to know how your code will scale.

> The world we live in today consists of complicated apps and software, each running on various devices and each having different capabilities. Some devices like desktops can run heavy machine learning software, but others like phones can only run apps. So when you create an application, you’ll need to optimize your code so that it runs smoothly across devices to give you an edge over your competitors. ⏤ [Big O Notation Cheat Sheet](https://flexiple.com/algorithms/big-o-notation-cheat-sheet)

*In computer science, Big O Notation is a mathematical function used to determine the difficulty of an algorithm.* Efficiency is measured in two ways: time complexity and space complexity:-

- *Time complexity*
  - measure of how fast an algorithm runs, it describes the amount of time necessary to execute an algorithm.
  - It is not a measure of the actual time taken to run an algorithm, instead, it is a measure of how the time taken scales with change in the input length. so we are not talking about seconds or milliseconds, or how many cycles it takes to run an algorithm, but rather how many operations it takes to run an algorithm as *a function of the size of the input*.
- *Space complexity*
  - measure of how much memory an algorithm takes up. simply compute how much space the variables in an algorithm/a program take up.
  - The best algorithms/programs should have the least space complexity. The lesser the space used, the faster it executes as *a function of the size of the input*.

the question now is *What's function of the size of the input 😂?*

to fully understand this, let's take an example of a function that takes an array of numbers and returns the sum of all the numbers in the array.

```js
function sum(arr) {
  let total = 0;
  for (let i = 0; i < arr.length; i++) {
    total += arr[i];
  }
  return total;
}
```

![function sum](./images/function-as-input.png)

Looking at the image above, we only have three statements. Still, because there is a loop, the second statement will be executed based on the input size, so if the input is four, the second statement (statement 2) will be executed four times, meaning the entire algorithm will run six (4 + 2) times.

we can see that the function has a for loop that iterates over the array and adds each element to the total variable, so the number of operations that the function will perform is equal to the number of elements in the array, so if the array has 10 elements, the function will perform 10 operations, if the array has 100 elements, the function will perform 100 operations, and so on.

In plain terms, the algorithm will run input + 2 times, where input can be any number. This shows that it's expressed in terms of the input. In other words, it is a function of the input size. ⏤ [Big O Cheat Sheet – Time Complexity Chart](https://www.freecodecamp.org/news/big-o-cheat-sheet-time-complexity-chart/)

In Big O, there are six major types of complexities (time and space):

- O(1) - Constant Time
- O(log n) - Logarithmic Time
- O(n) - Linear Time
- O(n log n) - Linearithmic Time
- O(n^2) - Quadratic Time
- O(2^n) - Exponential Time
- O(n!) - Factorial Time

the above list is sorted from the best to the worst, it basically used to express the performance of algorithms or the complexity of algorithms based on the input. so we can say that the best algorithm is the one that has the least time complexity and the worst algorithm is the one that has the highest time complexity.

![Big O Complexity Chart](./images/big-o-complexity-chart.png)

here are some rules to keep in mind when calculating the time complexity of an algorithm:

- growth is with respect to the input
- Constants are dropped
- Worst case is usually the way we measure

The next question that comes to mind is how you know which algorithm has which time complexity, given that this is meant to be a cheatsheet 😂.

- **Constant time complexity (O(1)):** Imagine you're doing different tasks, like solving puzzles or sorting toys. Sometimes, no matter how many toys you have, you solve them in the same time! That's like when it's constant time

*Example:*

```js
function firstToy(toys) {
  return toys[0];
}

const toys = ["ball", "car", "doll", "lego", "puzzle", "robot", "train"];
firstToy(toys); // "ball"
```

as you can see, the function above takes an array of toys and returns the first toy in the array, no matter how many toys are in the array, the function will always return the first toy, so it's constant time.

- **Logarithmic time complexity (O(log n)):** When you cut the number of things you're working with in half each time, and it helps you solve things faster. Like if you had 8 toys, it might take 3 guesses to find the right one, but if you had 16 toys, it only takes 4 guesses!

*Example:*

```js
function findToy(toys, toy) {
  let min = 0;
  let max = toys.length - 1;
  let guess;

  while (min <= max) {
    guess = Math.floor((min + max) / 2);

    if (toys[guess] === toy) {
      return guess;
    } else {
      if (toys[guess] < toy) {
        min = guess + 1;
      } else {
        max = guess - 1;
      }
    }
  }

  return -1;
}

const toys = ["ball", "car", "doll", "lego", "puzzle", "robot", "train"];
const toy = "lego";
findToy(toys, toy); // 3
```

the function above takes an array of toys and a toy, then it returns the index of the toy in the array, if the toy is not in the array, it returns -1, the function uses binary search algorithm to find the toy in the array, so it's logarithmic time.

- **Linear time complexity (O(n)):** When the time it takes to solve something grows as much as the number of things you have. When you have just one loop to solve a problem, the time it takes to solve things grows as much as the number of toys you have. Like if you have ten toys, it might take ten times longer than having just one toy

*Example:*

```js
function findToy(toys, toy) {
  for (let i = 0; i < toys.length; i++) {
    if (toys[i] === toy) {
      return i;
    }
  }

  return -1;
}

const toys = ["ball", "car", "doll", "lego", "puzzle", "robot", "train"];
const toy = "lego";
findToy(toys, toy); // 3
```

the function above takes an array of toys and a toy, then it returns the index of the toy in the array, if the toy is not in the array, it returns -1, the function uses linear search algorithm to find the toy in the array, so it's linear time.

- **Quadratic time complexity (O(n^2)):** When you're doing something with each thing for every other thing you have (loops inside loops). So if you have 3 toys and for each toy, you have to do something with every other toy, it's a lot more work and takes much longer.

*Example:*

```js
function findToy(toys) {
  for (let i = 0; i < toys.length; i++) {
    for (let j = 0; j < toys.length; j++) {
      console.log(toys[i], toys[j]);
    }
  }
}
const toys = ["ball", "car", "doll", "lego", "puzzle", "robot", "train"];
findToy(toys);
```

the function above takes an array of toys and prints each toy with every other toy in the array, so it's quadratic time.

- **Exponential time complexity (O(2^n)):** This is when adding just one more thing makes the work much, much harder. Like if you have 2 toys, it takes some time. But if you add just 1 more toy, it might take a lot longer than before, and adding more toys keeps making it way, way harder.

*Example:*

```js
function findToy(toys) {
  if (toys.length === 1) {
    return toys[0];
  }

  return findToy(toys.slice(1));
}

const toys = ["ball", "car", "doll", "lego", "puzzle", "robot", "train"];
findToy(toys);
```

the function above takes an array of toys and returns the first toy in the array, it uses recursion to solve the problem, In the code above, the algorithm specifies a growth rate that doubles every time the input data set is added. so it's exponential time.

> also, there are other complexities like Linearithmic time complexity (O(n log n)), Factorial time complexity (O(n!)), and Cubic time complexity (O(n^3)).

I recommend also to take a look at [Big O Cheat Sheet](https://www.bigocheatsheet.com/) as it has more samples and examples.

## References

- [Big O Cheat Sheet – Time Complexity Chart](https://www.freecodecamp.org/news/big-o-cheat-sheet-time-complexity-chart/)
- [Big O Notation Cheat Sheet](https://flexiple.com/algorithms/big-o-notation-cheat-sheet)
