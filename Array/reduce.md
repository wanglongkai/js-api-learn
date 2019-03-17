# Array.prototype.reduce
reduce()方法对数组中的每个元素执行一次我们提供的reducer函数（下标升序执行），将结果汇总为单个返回值。      
**遍历数组且只有一个返回值中的情况下，一般可以用这个方法**  
    

**reducer函数**接受4个参数：    
1. Accumulator(累计器)
2. CurentValue(当前值)
3. CurrentIndex(当前索引)
4. SourceArray(原数组)


## 语法
arr.reduce(callback,-initialValue);    
提供initialValue时，Accumulator的第一次值为initialValue，CurrentValue为数组第一项；    
不提供initialValue时，Accumulator的第一次值为数组第一项，CurrentValue为数组第二项。    
注意：`提供初始值(initialValue)通常更安全`    


## 举例
例1：
```javascript
let sum = [1,2,3,4,5].reduce((accu,cur,curindex,arr)=>{
	return accu+cur; 
},0);
console.log(sum);//15
```

例2：
```javascript
let sum = [{x:1},{x:2},{x:3}].reduce((accu,cur,curindex,arr)=>{
	return accu+cur.x;
},0);
console.log(sum);//6
```

例3：
```javascript
//将二维数组变成一维数组
let flat = [[0,1],[2,3,4],[5,6]].reduce((accu,cur)=>{
	return accu.concat(cur);
},[]);
console.log(flat);//[0,1,2,3,4,5,6]
```

例4：
```javascript
//计算数组中每个元素的出现次数
let names = ['Alice', 'Bob', 'Tiff', 'Bruce', 'Alice'];
let countObj = names.reduce((accu,cur)=>{
	if(cur in accu){
		accu[cur]++;
	}else{
		accu[cur] = 1;
	}
	return accu;
},{});
console.log(countObj);//{ 'Alice': 2, 'Bob': 1, 'Tiff': 1, 'Bruce': 1 }
```
