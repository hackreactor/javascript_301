# Part II: Arrays (Solutions)

### Basic Requirements

#### Creating Arrays

1. Using the array: `["cat", "fox", "dog", "monkey"]`, what is the index of:

   + "dog"?       // => 2
   + "monkey"?    // => 3
   + "cat"?       // => 0


2. Fix the syntax/style in the following arrays:

  ```js
  [ 1, 3 4 7,9, ]
  "the""quick""brown","fox" "jumped","over" the lazy, "dog",  ]
  [true false,true
  ```

  **FIXED:**
  ```js
  [1, 3, 4, 7, 9]
  ["the", "quick", "brown", "fox", "jumped", "over", "the", "lazy", "dog"]
  [true, false, true]
  ```

3. Create arrays in the *global scope* of your program consisting of strings that represent:

   + Your favorite TV shows/movies
   + Names of people you know/care about
   + Favorite sports/activities

#### Accessing Array Elements

1. Using the arrays that you created in the last exercise, use the console to access:

    + First elements,
    + Last elements,
    + Other elements!


2. Write a function `first` that takes an array as an argument and returns the
   first element in that array.

   **ANSWER:**
   ```js
   function first(arr) {
     return arr[0];
   }

3. Write a function `last` that takes an array as an argument and returns the
   *last* element in the array. **Hint:** What is the relationship between the
   *index* of the last element in the array and the *length* of the array?

   **ANSWER:**
   ```js
   function last(arr) {
     var lastIndex = arr.length - 1;
     return arr[lastIndex];
   }
   ```

#### Modifying Arrays

1. Using `push` and `unshift`, make this array contain the
   numbers from zero through seven:

   **ANSWER:**
   ```js
   var arr = [2, 3, 4];

   arr.unshift(1);
   arr.unshift(0);
   arr.push(5);
   arr.push(6);
   arr.push(7);

   arr; // => [0, 1, 2, 3, 4, 5, 6, 7]
   ```

2. What is *returned* by `push`? Before throwing this into the console, form a
   hypothesis about what you think the return value will be:

   ```js
   var arr = [5, 7, 9];
   arr.push(6); // => ???
   ```

   Were you correct? What is the returned by `push`? Does `unshift` work in the
   same way?

   **ANSWER:**
   Both .push() and .unshift() return the length of the *new* array.

3. We can use the *assignment operator* (`=`) to replace elements in arrays with
   other ones like so:

   ```js
   var animals = ['dog', 'elephant', 'zebra']
   // let's replace 'dog' with 'hippo'
   animals[0] = 'hippo';
   animals; // => ['hippo', 'elephant', 'zebra']
   ```

   Using the same principle, perform the following:

   ```js
   // 1. Change all odd numbers to be those numbers multiplied by two:
   var numbers = [4, 9, 7, 2, 1, 8];

   numbers[1] = numbers[1] * 2;
   numbers[2] = numbers[2] * 2;
   numbers[4] = numbers[4] * 2;

   numbers; // => [4, 18, 14, 2, 2, 8]

   // 2. Fix the typos by replacing each element with a correctly spelled version
   var places = ['snfranisco', 'oacklannd', 'santacrus']

   places[0] = 'san francisco';
   places[1] = 'oakland';
   places[2] = 'santa cruz';

   places; // => ['san francisco', 'oakland', 'santa cruz']
   ```

### More Practice

1. Write a function called `nth` that accepts an array and an index as
   parameters, and returns the element at that index.

   ```js
   function nth(array, index) {
     return array[index];
   }
   var animals = ['dog', 'cat', 'gerbil'];
   nth(animals, 2); // => 'gerbil'
   nth(animals, 1) === animals[1]; // => true
   ```

2. Write a function `rest` that returns all the elements in the array *except*
   for the first one. **HINT:** Read about the `slice` method on
   [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice)
   and/or experiment with `slice` at the console like so:

   ```js
   var numbers = [3, 2, 7, 5];
   numbers.slice(0);
   numbers.slice(1);
   numbers.slice(2);
   numbers.slice(0, 2);
   ```

   ```js
   function rest(arr) {
     return arr.slice(1);
   }
   ```

3. Write a function `butlast` that returns all of the elements in the array
   *except* for the last one (you may want to use `slice` for this one as well).

   ```js
   function butlast(arr) {
     return arr.slice(0, -1);
   }
   ```

4. Complete the function `cons` that accepts an element and an array, and
   returns an array with the element added to the *front* of the array:

   ```js
   function cons(x, array) {
     array.unshift(x);
     return array;
   }
   ```

5. Complete the function `conj` that accepts an array and an element, and
   returns an array with the element added to the *end* of the array:

   ```js
   function conj(array, x) {
     array.push(x);
     return array;
   }
   ```

6. What benefit(s) might there be to using functions like `cons` or `conj` over
   `unshift` or `push`?

   **ANSWER:**
   The array that we are modifying is being *returned* to us when we use these functions, whereas .unshift() and .push() return the array's new length. It is often the case that we want to perform addition operations using the array after it has been modified; using these functions makes doing so easier.

7. Try the following in a console:

   ```js
   var arr = [];
   arr[7] = "Hello."
   arr; // => ???
   ```

   What is the value of `arr` after assigning an element to its seventh index?
   Explain the result in plain English.

   **ANSWER:**
   The value of `arr` is an array with the following characteristics:
      * Length of 8
      * Contains 7 empty elements (indices 0-6)
      * Contains the string `"Hello."` as its 8th element (index 7)
   In order to assign a value at index 7 (`arr[7] = "Hello."`) JavaScript has inserted empty elements at all preceding indices. It may help to think of arrays like a collection of boxes in which we can store values, with each box representing an element at a given index. In order to have a value in our 8th box (`arr[7]`), we must have the other boxes that came before it, even if they are empty.

### Advanced

1. Without running the below function, use a whiteboard to figure out what it
   should return by repeatedly expanding function invocations:

   ```js
   function mystery(array) {
     if (array.length === 0) {
       return [];
     }
     return conj(mystery(rest(array)), first(array));
   }
   ```

2. Using `first`, `rest`, `conj` and/or `cons`, write functions that accomplish
   the following:

   ```js
   function first(arr) {
     return arr[0];
   }

   function rest(arr) {
     return arr.slice(1);
   }

   function cons(x, array) {
     array.unshift(x);
     return array;
   }

   function conj(array, x) {
     array.push(x);
     return array;
   }
   ```

   + `sum` all the elements of an array

   ```js
   function sumArray(arr) {
      var sum = 0;

      while (arr.length > 0) {
        sum = sum + first(arr);
        arr = rest(arr);
      }

      return sum;
   }
   ```

   + Given an array, returns a new array with each element *squared*

   ```js
   function squaredArray(arr) {
     var squaredArr = [];

     while (arr.length > 0) {
       var squaredNum = first(arr) * first(arr);
       conj(squaredArr, squaredNum);
       arr = rest(arr);
     }

     return squaredArr;
   }
   ```

   + Given an array of numbers, returns a new array of just the *even* numbers

   ```js
   function evenArray(arr) {
     var evenArr = [];

     while (arr.length > 0) {
       var current = first(arr);
       if (current % 2 === 0) {
         conj(evenArr, current);
       }
       arr = rest(arr);
     }

     return evenArr;
   }
   ```

   **HINT:** After figuring out how the `mystery` function works above, use it
   as a reference for how to write this type of function.
