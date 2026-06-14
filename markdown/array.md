#### map函数
~~~javaacript
arr.map(callback, thisArg)  
~~~
- callback：遍历回调
- thisArg（可选）：指定回调内的 this

~~~javascript
const 新数组 = 原数组.map( (元素, 索引, 原数组) => {
  // 处理逻辑，必须 return 结果
  return 新值;
});
~~~

- 元素：当前遍历的数组项（必用）
- 索引：当前项下标（可选）
- 原数组：遍历的原始数组（可选）

1. 返回新数组，原数组不变
1. 长度一致，必须有返回值


#### filter函数
~~~javaacript
arr.filter(callback, thisArg)  
~~~
- callback：遍历回调
- thisArg（可选）：指定回调内的 this
~~~javascript
 const 新数组 = 原数组.filter((元素, 索引, 原数组) => {
  // 条件判断，返回 true / false
  return 布尔值;
});
~~~
- 元素：当前遍历项（常用）
- 索引：当前项下标（可选）
- 原数组：遍历的原始数组（可选）
- 规则：return true 保留该项；return false 剔除该项