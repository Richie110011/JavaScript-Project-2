// --------------------
// String Manipulation
// --------------------

// Reverse a String
function reverseString(str) {
  return str.split("").reverse().join("");
}

// Count Characters
function countCharacters(str) {
  return str.length;
}

// Capitalize Words
function capitalizeWords(sentence) {
  return sentence
    .split(" ")
    .map(word => word.charAt(0).toUpperCase() + word.slice(1).toLowerCase())
    .join(" ");
}

// --------------------
// Array Functions
// --------------------

// Find Maximum
function findMax(arr) {
  return Math.max(...arr);
}

// Find Minimum
function findMin(arr) {
  return Math.min(...arr);
}

// Sum of Array
function sumArray(arr) {
  return arr.reduce((sum, num) => sum + num, 0);
}

// Filter Array (condition is a function like x => x > 3)
function filterArray(arr, condition) {
  return arr.filter(condition);
}

// --------------------
// Mathematical Functions
// --------------------

// Factorial
function factorial(n) {
  if (n < 0) throw new Error("Factorial not defined for negative numbers");
  let result = 1;
  for (let i = 2; i <= n; i++) {
    result *= i;
  }
  return result;
}

// Prime Number Check
function isPrime(n) {
  if (n <= 1) return false;
  if (n <= 3) return true;
  if (n % 2 === 0 || n % 3 === 0) return false;
  for (let i = 5; i * i <= n; i += 6) {
    if (n % i === 0 || n % (i + 2) === 0) return false;
  }
  return true;
}

// Fibonacci Sequence
function fibonacciTerms(n) {
  if (n <= 0) return [];
  if (n === 1) return [0];
  let seq = [0, 1];
  while (seq.length < n) {
    seq.push(seq[seq.length - 1] + seq[seq.length - 2]);
  }
  return seq;
}

// --------------------
// Example Tests
// --------------------

console.log("Reverse:", reverseString("hello"));           // "olleh"
console.log("Count:", countCharacters("hello world"));     // 11
console.log("Capitalize:", capitalizeWords("hello world")); // "Hello World"

let nums = [3, 1, 4, 1, 5, 9];
console.log("Max:", findMax(nums));     // 9
console.log("Min:", findMin(nums));     // 1
console.log("Sum:", sumArray(nums));    // 23
console.log("Filter > 3:", filterArray(nums, x => x > 3)); // [4, 5, 9]

console.log("Factorial(5):", factorial(5));   // 120
console.log("isPrime(7):", isPrime(7));       // true
console.log("Fibonacci(7):", fibonacciTerms(7)); // [0,1,1,2,3,5,8]
