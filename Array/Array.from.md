# Array.from()方法

**作用：根据一个类数组或可迭代对象创建一个新的数组实例**

### 语法
> Array.from(arrayLike,-mapFn,-thisArgs)

1. arrayLike
    * 想要转换成数组的类数组或可迭代对象
2. mapFn(可选)
    * 新数组中的每一个元素都会执行一次该回调函数
3. thisArgs(可选)
    * mapFn函数的this指向


### 实例

#### Array from a String
```
Array.from("foo");
//["f","o","o"]
```

#### Array from a Set
```
let set = new Set([1,2,3]);
Array.from(set);
//[1,2,3]
```

#### Array from an Array-like object(arguments)
```
function f(){
  return Array.from(arguments);
}
f(1,2,3);
//[1,2,3]
```

#### 在Array.from中使用`箭头函数`
*只能用箭头函数，不能有普通函数*
```
Array.from([1,2,3],x=>x*2);
//解释：
//1,根据[1,2,3]数组创建一个新的数组[1,2,3];
//2,新数组给每一项都要执行箭头函数
//3,得到结果每一项都乘以2---->[2,4,6]

Array.from({length:3},(v,i)=>i);
//解释：
//1,通过可迭代对象生成一个新数组，[undefined,undefined,undefined]
//2,新数组每一项执行箭头函数
//3,每一项的下标做为值。[1,2,3]
```
