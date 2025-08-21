# 🧑‍💻JavaScript数据结构与算法-HowieCong
> 务必要熟悉JavaScript使用再来学！

## 数组
- 在 JavaScript 中，数组是一种特殊的对象，用于存储多个值的有序集合

---

### 1. 数组的创建

```js
// 方括号+元素内容
const arr = [1,2,3]

// 构造函数，等价于 const arr = []
const arr2 = new Array();

// 长度为7的数组（注意：此时每个元素为empty，即未初始化）
const arr3 = new Array(7); // length: 7

// 创建一个长度确定、同时每一个元素的值也确定的数组
// 需求为每个元素的值为6，调用fill方法，给fill一个6
const arr4 = (new Array(7)).fill(6) // (7)[6,6,6,6,6,6,6]

// 使用扩展运算符复制数组
// 扩展运算符（...）可以用于复制一个数组，创建一个浅拷贝的新数组
const originalArr = [1, 2, 3];
const copiedArr = [...originalArr]; 
console.log(copiedArr); // [1, 2, 3]

// 使用Array.from()的映射功能
// Array.from()除了可以从类数组或可迭代对象创建数组，还可以接受一个映射函数作为第二个参数，对每个元素进行处理
const arr5 = Array.from([1, 2, 3], num => num * 2); 
console.log(arr5); // [2, 4, 6]
```

> **补充：**  
> - `Array()` 构造函数如果只传一个数字参数，会创建指定长度的空数组（每个元素为empty），不是undefined。  
> - 推荐优先使用字面量 `[]` 创建数组，语义更清晰。

---

### 2. 一维数组的访问和遍历

- 访问数组的元素,直接在中括号中指定其索引即可：

```js
arr[0] // 访问索引下标为0的元素
```

- 遍历数组常见方法：

> 如果没有特殊需要，统一使用for循环来实现遍历，从性能上看，for循环遍历起来是最快

#### （1）for循环
- 最基础的方法 => 通过循环数组的下标 => 依次访问值

```js
const len = arr.length;
for(let i = 0; i < len; i++){
    // 输出数组的元素值，输出当前索引
    console.log(arr[i], i)
}
```
> **修正：** 你的代码里 `arr.lengthh` 拼写错误，应为 `arr.length`。

#### （2）forEach方法
- 通过foreach方法中传入函数的第一个入参和第二个入参，也可以取到数组每个元素的值及其索引

```js
arr.forEach((item, index) => {
    // 输出数组的元素值，输出当前索引
    console.log(item, index)
})
```

#### （3）map方法
- 和foreach方法差不多，区别在map会根据传入的函数逻辑对数组每个元素进行处理，返回一个全新的数组，map不单是遍历，而是在遍历的基础上再加工。需要对数组内容做批量修改、同时修改的逻辑又要高度一致，就可以调用map来达到我们的目的

```js
const newArr = arr.map((item, index) =>{
    // 输出数组的元素值，输出当前索引
    console.log(item, index)
    // 在当前元素的值基础上加1
    return item + 1
})
// 通过map返回一个全新的数组，数组的每个元素的值都是再其现有元素值的基础上+1后的结果
```

#### （4）for...of循环
- `for...of` 循环是 ES6 引入的一种遍历可迭代对象的语法，数组是可迭代对象，因此可以使用 `for...of` 循环来遍历数组元素

```js
const arr = [1, 2, 3]; 
for (const item of arr) { 
    console.log(item); 
}
```

#### （5）for...in循环
- 虽然 `for...in` 循环主要用于遍历对象的可枚举属性，但也可以用于数组。不过需要注意的是，`for...in` 循环会遍历数组的所有可枚举属性，包括自定义的属性，并且遍历顺序可能不是按照数组索引的顺序

```js
const arr = [1, 2, 3];
arr.customProperty = 'hello'; 
for (const index in arr) { 
    console.log(index, arr[index]); 
}
```
> **补充：**  
> - 不推荐用 `for...in` 遍历数组，容易出现意外结果。
