# 🧑‍💻 JavaScript Data Structures & Algorithms - HowieCong

> **Tip:** Please make sure you are familiar with the basics of JavaScript before studying this content!

---

## Array

- In JavaScript, an array is a special type of object used to store an ordered collection of multiple values.

---

### 1. Creating Arrays

```js
// 1. Literal notation
const arr = [1, 2, 3];

// 2. Constructor (equivalent to const arr2 = [])
const arr2 = new Array();

// 3. Create an array with a specified length (each element is empty)
const arr3 = new Array(7); // length: 7

// 4. Create an array with a fixed length and value for each element
const arr4 = (new Array(7)).fill(6); // [6, 6, 6, 6, 6, 6, 6]

// 5. Use the spread operator to copy an array (shallow copy)
const originalArr = [1, 2, 3];
const copiedArr = [...originalArr];
console.log(copiedArr); // [1, 2, 3]

// 6. Use Array.from() with a mapping function
const arr5 = Array.from([1, 2, 3], num => num * 2);
console.log(arr5); // [2, 4, 6]
```

> **Note:**  
> - If the `Array()` constructor receives only one numeric argument, it creates an array of the specified length (each element is empty), not `undefined`.  
> - It is recommended to use the literal `[]` to create arrays for clearer semantics.

---

### 2. Accessing and Iterating One-dimensional Arrays

- To access an array element, simply specify its index in square brackets:

```js
arr[0]; // Access the element at index 0
```

#### Common Iteration Methods

> **Tip:** Unless you have special requirements, prefer using a `for` loop for iteration, as it offers the best performance.

---

#### (1) for Loop

- The most basic and efficient way to iterate through an array using indices.

```js
const len = arr.length;
for (let i = 0; i < len; i++) {
    console.log(arr[i], i); // Output element value and index
}
```

---

#### (2) forEach Method

- Use a callback function to access each element and its index.

```js
arr.forEach((item, index) => {
    console.log(item, index);
});
```

---

#### (3) map Method

- Iterate through the array and return a new array, commonly used for batch modification of elements.

```js
const newArr = arr.map((item, index) => {
    console.log(item, index);
    return item + 1; // Add 1 to each element
});
// newArr: each element is the original value plus 1
```

---

#### (4) for...of Loop

- Introduced in ES6, used to iterate over the values of iterable objects (such as arrays).

```js
const arr = [1, 2, 3];
for (const item of arr) {
    console.log(item);
}
```

---

#### (5) for...in Loop

- Mainly used for iterating over object properties; can be used for arrays but not recommended.

```js
const arr = [1, 2, 3];
arr.customProperty = 'hello';
for (const index in arr) {
    console.log(index, arr[index]);
}
```

> **Note:**  
> - `for...in` will iterate over all enumerable properties of the array (including custom properties), and the order is not guaranteed to follow the array indices.  
> - **Not recommended** for array iteration, as it may lead to unexpected results.

---

### 3. Two-dimensional Array

> A two-dimensional array is essentially an array of arrays, where each element is itself an array.  
> Compared to a one-dimensional array (like a line), a two-dimensional array is like a plane. In mathematics, such a rectangular arrangement of complex or real numbers is called a matrix, so a two-dimensional array is also known as a matrix.

```js
const arr = [
    [1, 2, 3],
    [1, 2, 3],
    [1, 2, 3],
    [1, 2, 3],
    [1, 2, 3]
];
```