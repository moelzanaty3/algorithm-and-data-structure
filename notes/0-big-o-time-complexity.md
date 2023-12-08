# Big O Time Complexity

Hi there 👋, in this note, we will talk about Big O Notation, what is it? why we need it? and how to use it?

- [Big O Time Complexity](#big-o-time-complexity)
  - [What is Big O Notation?](#what-is-big-o-notation)
  - [Why do we need Big O Notation?](#why-do-we-need-big-o-notation)
  - [Efficiency](#efficiency)
    - [Time complexity](#time-complexity)
    - [Space complexity](#space-complexity)
  - [Time Complexities](#time-complexities)
    - [Constant Time - O(1) Algorithm 🕒](#constant-time---o1-algorithm-)
    - [Logarithmic Time - O(log n) Algorithm 📉](#logarithmic-time---olog-n-algorithm-)
    - [Linear Time - O(n) Algorithm 📈](#linear-time---on-algorithm-)
    - [Quadratic Time - O(n²) Algorithm 🔄](#quadratic-time---on-algorithm-)
    - [Exponential Time - O(2^n) Algorithm 📈](#exponential-time---o2n-algorithm-)
  - [Key Considerations in Analyzing Time Complexity ⏱️](#key-considerations-in-analyzing-time-complexity-️)
  - [References](#references)

## What is Big O Notation?

In simple words, Big O is theoretical definition of the complexity of an algorithm as function of the size.a notation used to describe  complexity and what i mean by notation  is that it simplifies everything in the algorithm down into a single variable

Big O is a useful notation for  understanding both time and space  complexity but only when comparing  amongst algorithms that solve the same  problem  the last bit in that definition of Big O  is a function of the size and all this  means is that Big O measures complexity  as the input size grows because it's not  important to understand how an algorithm  performs in a single data set but in all  possible data sets  you will

also see Big O referred to as  the upper bound of the algorithm and  what that means is that Big O measures  how the algorithm performs in the worst  case scenario  so that's all Big O is  nothing special

> Tip💡: Imagine you're playing a game. Sometimes, things go perfectly from the start, and you finish quickly. That's like the best way things can happen! But there are times when things get really tricky, and it's harder to finish the game. We think about these tricky times because they help us make sure we're always doing at least as well as the hardest part. It's like knowing we'll always do our best or even better than the hardest part of the game!

## Why do we need Big O Notation?

- Yes, because it's important to know how long your code will take to run.
- It's important to know how much memory your code will take up.
- It's important to know how your code will scale.

> TIP💡: The world we live in today consists of complicated apps and software, each running on various devices and each having different capabilities. Some devices like desktops can run heavy machine learning software, but others like phones can only run apps. So when you create an application, you’ll need to optimize your code so that it runs smoothly across devices to give you an edge over your competitors. ⏤ [Big O Notation Cheat Sheet](https://flexiple.com/algorithms/big-o-notation-cheat-sheet)

## Efficiency

*In computer science, Big O Notation is a mathematical function used to determine the difficulty of an algorithm.* Efficiency is measured in two ways: time complexity and space complexity:-

### Time complexity

Basically it's a way to measure of how fast an algorithm runs, it describes the amount of time necessary to execute an algorithm. When ⏱️ analyzing an algorithm's time complexity, we encounter three scenarios: *best-case*, *average-case*, and *worst-case*, each portraying different performance scenarios. Suppose we have the following unsorted list [1, 5, 3, 9, 2, 4, 6, 7, 8] and we need to find the index of a value in this list using linear search.

- *Best-case*: 🌟 this is the complexity of solving the problem for the best input. In our example, the best case would be to search for the value 1. Since this is the first value of the list, it would be found in the first iteration.

- *Average-case*: 📊 this is the average complexity of solving the problem. This complexity is defined with respect to the distribution of the values in the input data. Maybe this is not the best example but, based on our sample, we could say that the average-case would be when we’re searching for some value in the “middle” of the list, for example, the value 2.

- *Worst-case*: ⚠️  this is the complexity of solving the problem for the worst input of size n. In our example, the worst-case would be to search for the value 8, which is the last element from the list.

Generally, when discussing an algorithm's time complexity, emphasis is often placed on *the worst-case* scenario as it illustrates the maximum time required for a given input size, providing a conservative estimation of performance.

It is not a measure of the actual time taken to run an algorithm, instead, it is a measure of how the time taken scales with change in the input length. so we are not talking about seconds or milliseconds, or how many cycles it takes to run an algorithm, but rather how many operations it takes to run an algorithm as *a function of the size of the input*.

### Space complexity

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

## Time Complexities

In Big O, there are six major types of complexities (time and space):

|       Name        | Time Complexity |
|-------------------|-----------------|
| Constant Time     |      O(1)       |
| Logarithmic Time  |    O(log n)     |
| Linear Time       |      O(n)       |
| Quasilinear Time  |   O(n log n)    |
| Quadratic Time    |     O(n^2)      |
| Exponential Time  |     O(2^n)      |
| Factorial Time    |      O(n!)      |

the above list is sorted from the best to the worst, it basically used to express the performance of algorithms or the complexity of algorithms based on the input. so we can say that the best algorithm is the one that has the least time complexity and the worst algorithm is the one that has the highest time complexity.

![Big O Complexity Chart](./images/big-o-complexity-chart.png)

The next question that comes to mind is how you know which algorithm has which time complexity 🤔

### Constant Time - O(1) Algorithm 🕒

- **Definition:** An algorithm operates in constant time (O(1)) when its execution is independent of the input data size (n). Regardless of the input's scale, the algorithm's runtime remains consistent.

- **Example:**

  ```js
  function getFirstFruit(fruits) {
    return fruits[0];
  }

  const fruits = ["🍎", "🍌", "🍇", "🍉", "🍊", "🍍", "🍓", "🍒"];
  getFirstFruit(fruits); // 🍎
  ```

- **Explanation:** The provided function `getFirstFruit` retrieves the first element from an array. Regardless of the array's length, the function's runtime remains constant because it only accesses the initial value.

> no matter how many fruits you have it will always return '🍎' which is the first fruit in the array, so it's constant time.

### Logarithmic Time - O(log n) Algorithm 📉

- **Definition:** An algorithm operates in logarithmic time complexity (O(log n)) when it reduces the size of the input data in each step without needing to examine all values.

> TIP💡: Logarithmic simply is the opposite of exponential, so if you have an exponential function like 2^x, the logarithmic function is log2(x).

![log-exponential](./images/log-exponential.png)

- **Example**

  ```javascript
  function binarySearch(numbersArr, value) {
    let left = 0
    let right = numbersArr.length - 1
    let guess

    while (left <= right) {
      const middle = Math.floor((left + right) / 2)
      guess = numbersArr[middle]
      if (guess === value) {
        return middle
      } else {
        if (guess > value) {
          right = middle - 1
        } else {
          left = middle + 1
        }
      }
    }
    throw new Error('Value is not in the list')
  }

  const numbersArr = [1, 2, 3, 4, 5, 6, 7, 8, 9]
  binarySearch(numbersArr, 8) // 7
  // 1st iteration => left = 0, right = 8, middle = 4, guess = 5, value = 8
  // 2nd iteration => left = 5, right = 8, middle = 6, guess = 7, value = 8
  // 3rd iteration => left = 7, right = 8, middle = 7, guess = 8, value = 8
  const fruits = ["🍎", "🍌", "🍇", "🍉", "🍊", "🍍", "🍓", "🍒"];
  binarySearch(fruits, "🍇"); // 2
  // 1st iteration => left = 0, right = 7, middle = 3, guess = "🍉", value = "🍇"
  // 2nd iteration => left = 0, right = 2, middle = 1, guess = "🍌", value = "🍇"
  // 3rd iteration => left = 2, right = 2, middle = 2, guess = "🍇", value = "🍇"
  ```

- **Explanation:** The `binarySearch` function locates the position of an element in a sorted list using the binary search algorithm. It repeatedly divides the search interval in half until the value is found or the search space becomes empty.

- **Binary Search Steps:**
    1. Calculate the middle of the list.
    2. Adjust the boundaries based on whether the value is greater or smaller than the middle element.
    3. Continue dividing the search space until the value is found or the boundaries converge.

> TIP💡: Algorithms with logarithmic time complexity are frequently employed in binary trees or binary search operations. They efficiently handle large datasets by reducing the search space with each iteration, making them highly efficient for sizable inputs.

often hear algorithms with logarithmic called sublinear algorithms, which is a more general term that includes any algorithm that is less than linear time complexity, normally becuase it's more efficient than linear time complexity.

### Linear Time - O(n) Algorithm 📈

- **Definition:** An algorithm operates in linear time complexity (O(n)) when its running time increases at most linearly with the size of the input data. It examines all values in the input data, and this complexity represents the best possible scenario for such algorithms.

- **Example**

  ```javascript
  function linearSearch(fruits, fruit) {
      for (let index = 0; index < fruits.length; index++) {
          if (fruit === fruits[index]) {
              return index; // Return index if value is found
          }
      }
      throw new Error('fruit not found in the list');
  }

  const fruits = ["🍎", "🍌", "🍇", "🍉", "🍊", "🍍", "🍓", "🍒"];
  linearSearch(fruits, "🍇"); // 2
  // 1st iteration => index = 0, value = "🍎"
  // 2nd iteration => index = 1, value = "🍌"
  // 3rd iteration => index = 2, value = "🍇"
  ```

- **Explanation:** The `linearSearch` function performs a linear search in an unsorted array to find the position of an element. It iterates through each element in the array and compares it with the desired value until a match is found.

- **Linear Search Steps:**
    1. Iterate through each element in the array.
    2. Check if the current element matches the value being searched.
    3. Return the index if the value is found, or raise an error if not found after examining all elements.

### Quadratic Time - O(n²) Algorithm 🔄

- **Definition:** An algorithm operates in quadratic time complexity (O(n²)) when it needs to perform a linear time operation for each value in the input data. This complexity arises when operations are nested, leading to exponential growth in execution time as the input size increases.

- **Example**

  ```javascript
  function bubbleSort(numbersArr) {
    let swapped
    do {
      swapped = false
      for (let i = 0; i < numbersArr.length - 1; i++) {
        if (current > next) {
        // Swap elements using destructuring assignment
          [numbersArr[i], numbersArr[i + 1]] = [numbersArr[i + 1], numbersArr[i]];
          swapped = true
        }
      }
    } while (swapped)
  }

  const numbersArr = [2, 5, 1, 4, 3]
  bubbleSort(numbersArr)
  // 1st Iteration 2,1,5,4,3 => index: 1, Swapped 5 and 1 => 2,1,5,4,3
  // 2nd Iteration 2,1,5,4,3 => index: 2, Swapped 5 and 4 => 2,1,4,5,3
  // 3rd Iteration 2,1,4,5,3 => index: 3, Swapped 5 and 3 => 2,1,4,3,5
  // 4th Iteration 2,1,4,3,5 => index: 4, Swapped 4 and 3 => 2,1,3,4,5
  // 5th Iteration 2,1,3,4,5 => index: 5, Swapped 2 and 1 => 1,2,3,4,5
  const fruits = ["🍎", "🍌", "🍇", "🍉", "🍊", "🍍", "🍓", "🍒"];
  bubbleSort(fruits);
  // 1st Iteration 🍎,🍌,🍇,🍉,🍊,🍍,🍓,🍒 => index: 1, Swapped 🍌 and 🍎 => 🍌,🍎,🍇,🍉,🍊,🍍,🍓,🍒
  // 2nd Iteration 🍌,🍎,🍇,🍉,🍊,🍍,🍓,🍒 => index: 2, Swapped 🍇 and 🍎 => 🍌,🍇,🍎,🍉,🍊,🍍,🍓,🍒
  // 3rd Iteration 🍌,🍇,🍎,🍉,🍊,🍍,🍓,🍒 => index: 3, Swapped 🍉 and 🍎 => 🍌,🍇,🍉,🍎,🍊,🍍,🍓,🍒
  // 4th Iteration 🍌,🍇,🍉,🍎,🍊,🍍,🍓,🍒 => index: 4, Swapped 🍊 and 🍎 => 🍌,🍇,🍉,🍊,🍎,🍍,🍓,🍒
  // 5th Iteration 🍌,🍇,🍉,🍊,🍎,🍍,🍓,🍒 => index: 5, Swapped 🍍 and 🍎 => 🍌,🍇,🍉,🍊,🍍,🍎,🍓,🍒
  // 6th Iteration 🍌,🍇,🍉,🍊,🍍,🍎,🍓,🍒 => index: 6, Swapped 🍓 and 🍎 => 🍌,🍇,🍉,🍊,🍍,🍓,🍎,🍒
  // 7th Iteration 🍌,🍇,🍉,🍊,🍍,🍓,🍎,🍒 => index: 7, Swapped 🍒 and 🍎 => 🍌,🍇,🍉,🍊,🍍,🍓,🍒,🍎
  // 8th Iteration 🍌,🍇,🍉,🍊,🍍,🍓,🍒,🍎 => index: 8, Swapped 🍒 and 🍎 => 🍌,🍇,🍉,🍊,🍍,🍓,🍒,🍎
  ```

- **Explanation:** The `bubbleSort` function implements the bubble sort algorithm, which has quadratic time complexity. It repeatedly steps through the array, compares adjacent elements, and swaps them if they are in the wrong order. This process continues until the entire array is sorted.

- **Bubble Sort Steps:**
    1. Compare each element with its adjacent element.
    2. Swap elements if they are in the wrong order.
    3. Repeat this process until the array is sorted.

- **Importance:** Quadratic time complexity algorithms, like bubble sort, perform comparisons for each element, resulting in increased time as the input size grows. This makes them less efficient for large datasets compared to algorithms with lower complexities.

The provided JavaScript code demonstrates the bubble sort algorithm using a sample array of fruits for sorting, showcasing the quadratic time complexity.

### Exponential Time - O(2^n) Algorithm 📈

- **Definition:** An algorithm operates in exponential time complexity (O(2^n)) when its growth rate doubles with each addition to the input data set. These algorithms are often found in brute-force methods and recursive computations.

- **Explanation:** Exponential time complexity becomes notably resource-intensive as the input size increases. Brute-force attacks, such as systematically checking all possible elements of a password, exemplify this complexity. Longer passwords become considerably more secure due to the exponentially increasing resources required to crack them compared to shorter ones.

- **Example: Recursive Fibonacci Algorithm**

  ```javascript
  function fibonacci(n) {
      if (n <= 1) {
          return n;
      }
      return fibonacci(n - 1) + fibonacci(n - 2);
  }

  fibonacci(4));
  ```

- **Explanation of Recursive Function:** The `fibonacci` function calculates Fibonacci numbers using a recursive approach. As the value of 'n' increases, the number of recursive calls grows exponentially, leading to a significant increase in computation time.

- **Visualization:** The Fibonacci recursion tree demonstrates how the number of function calls grows exponentially with increasing 'n':
  - [Recursion Tree of Fibonacci(4)](https://visualgo.net/bn/recursion)
  - [Recursion Tree of Fibonacci(6)](https://visualgo.net/bn/recursion)

- **Importance:** Exponential time complexity algorithms, like the recursive Fibonacci computation, showcase the immense resource requirements and computational burden as the input size expands. Understanding such complexities is crucial when designing efficient algorithms.

> TIP💡: there are other complexities like Linearithmic time complexity (O(n log n)), Factorial time complexity (O(n!)), and Cubic time complexity (O(n^3)).

## Key Considerations in Analyzing Time Complexity ⏱️

- **Algorithmic Complexity Analysis Rules:**
  - **Growth Relative to Input:** Time complexity analysis considers the growth pattern concerning the input size.
  - **Disregarding Constants:** Constants in time complexity calculations are omitted since they don't significantly affect scalability.
  - **Emphasis on Worst Case Scenario:** Evaluating the algorithm's worst-case scenario provides a crucial measurement of its efficiency.
  - **Largest Complexity Among Operations:** When an algorithm comprises multiple operations, its time complexity is defined by the operation with the most substantial impact on execution time.
  - **Focus on Input:** Time complexity focuses on how an algorithm's runtime scales concerning changes in input size.
  - **Neglecting Constants:** Discarding constants aids in understanding the algorithm's growth trend without the influence of negligible factors.

This set of rules guides the analysis of time complexity, emphasizing the significance of considering the most influential operation, disregarding constants, and prioritizing worst-case scenarios for accurate assessments.

I recommend also to take a look at [Big O Cheat Sheet](https://www.bigocheatsheet.com/) as it has more samples and examples.

## References

- [Computational complexity](https://en.wikipedia.org/wiki/Computational_complexity)
- [Big-O notation](https://en.wikipedia.org/wiki/Big_O_notation)
- [Time complexity](https://en.wikipedia.org/wiki/Time_complexity)
- [Big O Cheat Sheet – Time Complexity Chart](https://www.freecodecamp.org/news/big-o-cheat-sheet-time-complexity-chart/)
- [Big O Notation Cheat Sheet](https://flexiple.com/algorithms/big-o-notation-cheat-sheet)
