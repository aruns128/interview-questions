1. Write a JavaScript function that finds and returns the maximum and minimum values in the array.

```javascript
function findMinMax(arr) {
  if (arr.length === 0) {
    return { min: undefined, max: undefined };
  }

  let min = arr[0];
  let max = arr[0];

  for (let i = 1; i < arr.length; i++) {
    if (arr[i] < min) {
      min = arr[i];
    }
    if (arr[i] > max) {
      max = arr[i];
    }
  }

  return { min, max };
}

// Example usage:
const numbers = [3, 9, 1, 7, 4, 12, -5, 8];
const result = findMinMax(numbers);
console.log(`Minimum: ${result.min}, Maximum: ${result.max}`);
```

2. Write a JavaScript function that removes duplicates from an array and returns a new array with unique values. For example, if given [1, 2, 2, 3, 4, 4, 5], the function should return [1, 2, 3, 4, 5].

```javascript
function removeDuplicates(arr) {
  return Array.from(new Set(arr));
}

// Example usage:
const inputArray = [1, 2, 2, 3, 4, 4, 5];
const uniqueArray = removeDuplicates(inputArray);
console.log(uniqueArray); // [1, 2, 3, 4, 5]
```

3. Write a JavaScript function that flattens a nested array. For example, if given [1, [2, [3, 4], 5], 6], the function should return [1, 2, 3, 4, 5, 6].

```javascript
function flattenArray(arr) {
  return arr.reduce((flat, item) => {
    return flat.concat(Array.isArray(item) ? flattenArray(item) : item);
  }, []);
}

// Example usage:
const nestedArray = [1, [2, [3, 4], 5], 6];
const flatArray = flattenArray(nestedArray);
console.log(flatArray); // [1, 2, 3, 4, 5, 6]
```

4. Create a JavaScript function that takes a sorted array of numbers and a target value and returns the index of the target value in the array using binary search. If the target value is not in the array, return -1.

```javascript
function binarySearch(arr, target) {
  let left = 0;
  let right = arr.length - 1;

  while (left <= right) {
    const mid = Math.floor((left + right) / 2);

    if (arr[mid] === target) {
      return mid;
    } else if (arr[mid] < target) {
      left = mid + 1;
    } else {
      right = mid - 1;
    }
  }

  return -1;
}

// Example usage:
const sortedArray = [1, 3, 5, 7, 9, 11, 13];
const targetValue = 7;
const resultIndex = binarySearch(sortedArray, targetValue);
console.log(resultIndex); // 3 (7 is found at index 3)
```

5. **Object-Oriented Programming (OOP):**
   Question: Create a `Person` class with a constructor that takes a name and age as parameters. Add a method that returns a greeting.

   ```javascript
   class Person {
     constructor(name, age) {
       this.name = name;
       this.age = age;
     }
     greet() {
       return `Hello, my name is ${this.name} and I'm ${this.age} years old.`;
     }
   }

   const person = new Person("Alice", 25);
   console.log(person.greet());
   ```

6. **Arrays and Objects:**
   Question: Given an array of numbers, write a function to calculate the sum of all the even numbers in the array.

   ```javascript
   function sumEvenNumbers(numbers) {
     return numbers.reduce((sum, number) => (number % 2 === 0 ? sum + number : sum), 0);
   }
   ```

7. ```javascript
   const output = {
     name: "Javascript",
     findName: function () {
       console.log(this.name);
     },
   };

   const fn = output.findName;
   fn();
   ```

a. Javascript b.undefined c.error d.none of these

it is not directly called, it will assigned to the global, then it will undefined in global variable.

8. when working with multiple Promises in parallel, which method is used to wait for all promises to resolve ?

```javascript
a.Promises.race();
b.Promises.any();
c.Promises.all();
d.Promises.resolveAll();
```

answer c

9. null == 0;
   [] == 0;
   null == [];

   a. true,true,true b. false,true,true
   c.false,true,false d. None of these

   answer c

10. ````javascript
        const obj = {
          name: "javascript",
        };
        obj.**proto** = Array.prototype;
    console.log(Array.isArray(obj));
    console.log(obj instanceof Array)

        ```
        false, true
    ````

```

```

11. ```javascript
    function doSomthing() {
      let a = 5;
      {
        var a = 6;
        console.log(a);
      }
      console.log(a);
    }
    doSomthing();
    ```

    Identifier 'a' has already been declared

12. return only duplicate element in the array using javascript [1, 2, 2, 3, 4, 4, 5, 6, 6];

```javascript
function findDuplicates(arr) {
  const seen = {};
  const duplicates = [];

  for (const item of arr) {
    if (seen[item]) {
      if (!duplicates.includes(item)) {
        duplicates.push(item);
      }
    } else {
      seen[item] = 1;
    }
  }

  return duplicates;
}

function findDuplicates(arr) {
  return arr.reduce((acc, val, index, array) => {
    if (array.indexOf(val, index + 1) !== -1 && acc.indexOf(val) === -1) {
      acc.push(val);
    }
    return acc;
  }, []);
}

const myArray = [1, 2, 2, 3, 4, 4, 5, 6, 6];
const duplicateElements = findDuplicates(myArray);
console.log(duplicateElements); // Output: [2, 4, 6]
```

const myArray = [1, 2, 2, 3, 4, 4, 5, 6, 6];

13. reverse each word in a sentence using javascript.
    example : i am a react js developer

```javascript
function reverseWords(sentence) {
  // Split the sentence into words
  const words = sentence.split(" ");

  // Reverse each word
  const reversedWords = words.map((word) => {
    return word.split("").reverse().join("");
  });

  // Join the reversed words back into a sentence
  const reversedSentence = reversedWords.join(" ");

  return reversedSentence;
}

const inputSentence = "i am a react js developer";
const reversedSentence = reverseWords(inputSentence);
console.log(reversedSentence); // Output: "i ma a tcaer js repoleved"
```

14. ````javascript
        let letters = ["a", "b", "c", "d", "e"];
        letters.push("f");
        letters.splice(0, 2);
        letters = [...letters, "g"];
        console.log(letters);
        ```
    [ "c", "d", "e","f","g"]
    ````

```javascript
15. class Bird {
      constructor() {
        console.log("i am a bird");
      }
    }

class Flamingo extends Bird {
  constructor() {
    console.log("I am pink");
  }
}

Uncaught ReferenceError: Must call super constructor in derived class before accessing 'this' or returning from derived constructor

class Bird {
  constructor(){
    console.log("i am a bird");
  }
}

class Flamingo extends Bird{
  constructor(){
    super()
    console.log("I am pink");
  }
}
```

```javascript
16. let a = 3;
    let b = new Number(3);
    let c = 3;
    console.log(a===b)
    console.log(a===b)
    console.log(b===c)
    false,false,false
```

```javascript
16. const a = [1,2,3]
const b = "1,2,3"
console.log(a==b)
```

```javascript
17. simple promise javascript example
const myPromise = new Promise((resolve, reject) => {
  // You can perform some asynchronous task here
  // For example, a setTimeout to simulate an async operation
  setTimeout(() => {
    const success = true; // You can replace this with your actual condition
    if (success) {
      resolve("Promise fulfilled!"); // Promise is resolved
    } else {
      reject("Promise rejected!"); // Promise is rejected
    }
  }, 2000); // Simulating a 2-second asynchronous task
});

myPromise
  .then((result) => {
    console.log(result); // This will run if the promise is resolved
  })
  .catch((error) => {
    console.error(error); // This will run if the promise is rejected
  });
```

```javascript
//object methods
const obj = { a: 1, b: 2, c: 3 };

//get out put like ['a','b','c']
const keys = Object.keys(obj);

//get out put like [1,2,3]
const values = Object.values(obj);

//get out put like [['a',1],['b',2],['c',3]]
const entries = Object.entries(obj);
```
