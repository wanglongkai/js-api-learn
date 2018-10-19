# Array.from()方法

### 作用：根据一个类数组或可迭代对象创建一个新的数组实例

### 语法

Array.from(arrayLike,-mapFn,-thisArgs)

1. arrayLike
    想要转换成数组的类数组或可迭代对象
2. mapFn(可选)
    新数组中的每一个元素都会执行一次该回调函数
3. thisArgs(可选)
    mapFn函数的this指向


### 实例

#### Array from a String
`
Array.from("foo");
//["f","o","o"]
`
