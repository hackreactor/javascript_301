# Part III: Array Iteration (Solutions)

### Basic Requirements

1. Write a function `sum` that computes the sum of the numbers in an array.

  ```js
  function sumFor(nums) {
    var total = 0;
    for (var i = 0; i < nums.length; i = i + 1) {
      total = total + nums[i];
    }
    return total;
  }

  function sumWhile(nums) {
    var total = 0;
    var i = 0;
    while (i < nums.length) {
      total = total + nums[i];
      i = i + 1;
    }
    return total;
  }
  ```

2. Write a function `max` that accepts an array of numbers and returns the
   *largest* number in the array.

  ```js
  function maxFor(nums) {
    var largest = nums[0];
    for (var i = 0; i < nums.length; i = i + 1) {
      if (nums[i] > largest) {
        largest = nums[i];
      }
    }
    return largest;
  }

  function maxWhile(nums) {
    var largest = nums[0];
    var i = 0;
    while (i < nums.length) {
      if (nums[i] > largest) {
        largest = nums[i];
      }
      i = i + 1;
    }
    return largest;
  }
  ```

3. Try the following at a console:

  ```js
  "the quick brown fox jumped over the lazy dog".split(" ");
  "Hello, world!".split("")
  "1,2,3,4,5,6".split(",")
  ```

  What is returned by `split` (You can read more about it
  [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split)),
  and how does it work?

  **ANSWER:**
  The split() method splits a string into an array of strings by separating the string into substrings, using a specified separator string to determine where to make each split. This separator string is the argument passed to .split(). The return value is the array of substrings.

  Use `split` to write a function `longestWord` that takes a string as an
  argument and returns the longest word.

  ```js
  function longestWordFor(str) {
    var split = str.split(' ');
    var longest = split[0];
    for (var i = 0; i < split.length; i = i + 1) {
      if (split[i].length > longest.length) {
        longest = split[i];
      }
    }
    return longest;
  }
  longestWordFor('all your base are belong to us') // => 'belong';

  function longestWordWhile(str) {
    var split = str.split(' ');
    var longest = split[0];
    var i = 0;
    while (i < split.length) {
      if (split[i].length > longest.length) {
        longest = split[i];
      }
      i = i + 1;
    }
    return longest;
  }
  longestWordWhile('all your base are belong to us') // => 'belong';
  ```

4. Write a function `remove` that accepts an *array* and an *element*, and
   returns an array with all ocurrences of *element* removed.

  ```js
  function removeFor(array, element) {
   var removed = [];
   for (var i = 0; i < array.length; i = i + 1) {
     if (array[i] !== element) {
       removed.push(array[i]);
     }
   }
   return removed;
  }
  removeFor([1, 3, 6, 2, 3], 3); // => [1, 6, 2]

  function removeWhile(array, element) {
  var removed = [];
  var i = 0;
  while (i < array.length) {
    if (array[i] !== element) {
       removed.push(array[i]);
     }
     i = i + 1;
  }
  return removed;
  }
  removeWhile([1, 3, 6, 2, 3], 3); // => [1, 6, 2]
  ```

5. Write a function `evens` that accepts an array as an argument, and returns
   an array consisting of all of the *even* numbers in that array.

  ```js
  function evensFor(array) {
    var evenNums = [];
    for (var i = 0; i < array.length; i = i + 1) {
      if (array[i] % 2 === 0) {
        evenNums.push(array[i]);
      }
    }
    return evenNums;
  }
  evensFor([1, 2, 3, 4, 5, 6, 7, 8]) // => [2, 4, 6, 8];

  function evensWhile(array) {
    var evenNums = [];
    var i = 0;
    while (i < array.length) {
      if (array[i] % 2 === 0) {
        evenNums.push(array[i]);
      }
      i = i + 1;
    }
    return evenNums;
  }
  evensWhile([1, 2, 3, 4, 5, 6, 7, 8]) // => [2, 4, 6, 8];
  ```

### More Practice

1. Write a function called `average` that takes an array of numbers as a
   parameter and returns the *average* of those numbers.

  ```js
  function averageFor(array) {
    var result = 0;
    for (var i = 0; i < array.length; i = i + 1) {
      result = result + array[i];
    }
    return result / array.length;
  }
  averageFor([1, 2, 3, 4, 5]) // => 3;

  function averageWhile(array) {
    var result = 0;
    var i = 0;
    while (i < array.length) {
      result = result + array[i];
      i = i + 1;
    }
    return result / array.length;
  }
  averageWhile([1, 2, 3, 4, 5]) // => 3;
  ```

2. Write a function called `min` that finds the *smallest* number in an array of
   numbers.

  ```js
  function minFor(array) {
    var min = array[0];
    for (var i = 0; i < array.length; i++) {
      if (array[i] < min) {
        min = array[i];
      }
    }
    return min;
  }
  minFor([10, 12, 5, 15, 20]) // => 5;

  function minWhile(array) {
    var min = array[0];
    var i = 0;
    while (i < array.length) {
      if (array[i] < min) {
        min = array[i];
      }
      i = i + 1;
    }
    return min;
  }
  minWhile([10, 12, 5, 15, 20]) // => 5;
  ```

3. Write a function `shortestWord` that works like `longestWord`, but returns
   the *shortest* word instead.

  ```js
  function shortestWordFor(str) {
    var split = str.split(' ');
    var shortest = split[0];
    for (var i = 0; i < split.length; i = i + 1) {
      if (split[i].length < shortest.length) {
        shortest = split[i];
      }
    }
    return shortest;
  }
  shortestWordFor('all your base are belong to us') // => 'to';

  function shortestWordWhile(str) {
    var split = str.split(' ');
    var shortest = split[0];
    var i = 0;
    while (i < split.length) {
      if (split[i].length < shortest.length) {
        shortest = split[i];
      }
      i = i + 1;
    }
    return shortest;
  }
  shortestWordWhile('all your base are belong to us') // => 'to';
  ```

4. Write a function `countChar` that takes two arguments: any string, and a
   *character* (string of one letter), and returns the number of times that the
   character occurs in the string.

  ```js
  function countCharFor(str, char) {
    var occurances = 0;
    for (var i = 0; i < str.length; i = i + 1) {
      if (str[i] === char) {
        occurances = occurances + 1;
      }
    }
    return occurances;
  }
  countCharFor('hello world', 'o') // => 2;

  function countCharWhile(str, char) {
    var occurances = 0;
    var i = 0;
    while (i < str.length) {
      if (str[i] === char) {
        occurances = occurances + 1;
      }
      i = i + 1;
    }
    return occurances;
  }
  countCharWhile('hello world', 'o') // => 2;
  ```

5. Write a function `evenLengthWords` that takes an array of *strings* as an
   argument, and returns an array of just the words that have an even length.

  ```js
  function evenLengthWordsFor(strings) {
    var result = [];
    for (var i = 0; i < strings.length; i = i + 1) {
      if (strings[i].length % 2 === 0) {
        result.push(strings[i]);
      }
    }
    return result;
  }
  evenLengthWordsFor(['hello', 'world', 'I', 'am', 'here']) // => ['am', 'here'];

  function evenLengthWordsWhile(strings) {
    var result = [];
    var i = 0;
    while (i < strings.length) {
      if (strings[i].length % 2 === 0) {
        result.push(strings[i]);
      }
      i = i + 1;
    }
    return result;
  }
  evenLengthWordsWhile(['hello', 'world', 'I', 'am', 'here']) // => ['am', 'here'];
  ```

### Advanced

1. Read about the `join` method on
   [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join)
   and use it to implement a function that accepts a string as an argument and
   returns that string *reversed*.

  ```js
  function reverseString(str) {
    return str.split('').reverse().join('');
  }
  reverseString('hello') // => 'olleh';
  ```

2. Write a function `keep` that "keeps" certain elements in an array. The
   function will need to take *two* arguments, an array, and something else --
   the second argument will be what is used to determine which elements to keep.

  ```js
  function keep(array, fn) {
    var result = [];
    for (var i = 0; i < array.length; i = i + 1) {
      if (fn(array[i]) === true) {
        result.push(array[i]);
      }
    }
    return result;
  }
  ```

   You should be able to use this function to write `evens`, `evenLengthWords`,
   a hypothetical `odds` function, or `oddLengthWords` *without changing the
   `keep` function*.
