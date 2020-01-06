# Part I: While (Solutions)

### Basic Requirements

1. **Summation to `n`:** Let's implement the function `sum` that takes a single
   parameter `n`, and computes the sum of all integers up to `n` starting from
   `0`.

   **ANSWER:**
   ```js
   function sum(n) {
     var current = 0;
     var sum = 0;

     while (current <= n) {
       sum = sum + current;
       current = current + 1;
     }

     return sum;
   }
   sum(3); // => 6
   sum(4); // => 10
   sum(5); // => 15
   ```

2. **Factorial of `n`:** The factorial of `n` is the *product* of all the
   integers preceding `n`, starting with `1`.

   **ANSWER:**
   ```js
   function factorial(n) {
     var current = 1;
     var product = 1;

     while (current < n) {
       product = product * current;
       current = current + 1;
     }

     return product;
   }
   factorial(3); // => 6
   factorial(4); // => 24
   factorial(5); // => 120
   ```

3. **Repeating a String `n` Times:** Let's write a function called
   `repeatString` that takes two parameters: a string `str`, which is the string
   to be repeated, and `count` -- a number representing how many times the
   string `s` should be repeated.

   **ANSWER:**
   ```js
   function repeatString(str, count) {
     var finalString = '';
     var start = 0;

     while (start < count) {
       finalString = finalString + str;
       start = start + 1;
     }

     return finalString;
   }
   repeatString('dog', 0); // => ''
   repeatString('dog', 1); // => 'dog'
   repeatString('dog', 2); // => 'dogdog'
   repeatString('dog', 3); // => 'dogdogdog'
   ```

   Your task is to implement the `repeatString` function using a `while` loop.

### More Practice

1. Modify your `sum` function from the **Basic Requirements** section to accept
   *two* parameters, `start` and `end`: `sum` should now compute the sum of the
   numbers from `start` to `end`.

   **ANSWER:**
   ```js
   function sum(start, end) {
     var current = start;
     var sum = 0;

     while (current <= end) {
       sum = sum + current;
       current = current + 1;
     }

     return sum;
   }
   sum(2, 7); // => 2 + 3 + 4 + 5 + 6 + 7 => 27
   sum(3, 5); // => 3 + 4 + 5 => 12
   ```

   + What happens if `start` is larger than `end`? Modify `sum` to check for this
     case and, when found, swap the `start` and `end` arguments.

  **ANSWER:**
   ```js
   function sum(start, end) {
     var current = start;
     var sum = 0;

     if (start > end) {
       current = end;
       end = start;
     }

     while (current <= end) {
       sum = sum + current;
       current = current + 1;
     }

     return sum;
   }
   sum(2, 7); // => 2 + 3 + 4 + 5 + 6 + 7 => 27
   sum(3, 5); // => 3 + 4 + 5 => 12
   ```

2. Let's pretend for a moment that JavaScript does not have the addition
   operator `+` -- instead, it comes with two functions called `inc` and `dec`
   that perform *increment* and *decrement* respectively:

   **ANSWER:**
   ```js
   // ignore the fact that inc makes use of +
   function inc(x) {
     return x + 1;
   }

   function dec(x) {
     return x - 1;
   }
   ```

   Your task is to write a function called `add` that takes two numbers as
   parameters, `x` and `y`, and adds them together. The catch is that you can
   *only* use `inc` and `dec` to accomplish this.

   **ANSWER:**
   ```js
   function add(x, y) {
     var sum = x;

     while (y > 0) {
       sum = inc(sum);
       y = dec(y);
     }

     return sum;
   }
   ```

3. Write a function called `isEven` that, given a number `n` as a parameter,
   returns `true` if that number is *even*, and `false` otherwise; however, you
   need to do this **without using the `%` operator.**

   **ANSWER:**
   ```js
   function isEven(n) {
     while (n > 0) {
       n = n - 2;
     }

     if (n === 0) {
       return true;
     }
     return false;
   }
   ```

4. Write a function called `multiply` that accepts two numbers as parameters,
   and multiplies them together -- but without using the `*` operator; instead,
   you'll need to use repeated addition.

   **ANSWER:**
   ```js
   function multiply(x, y) {
     var product = 0;

     while (y > 0) {
       product = product + x;
       y = y - 1;
     }

     return product;
   }
   ```
