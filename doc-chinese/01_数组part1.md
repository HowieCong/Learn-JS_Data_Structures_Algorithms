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