## reduce
```
const values: any = [1, 2, 3, 4, 5]; const sum: number = (values as number[]).reduce((acc, val) => acc + val, 0); console.log(sum); // 输出：15
```
reduce 接受一个回调函数，acc是累加器，val是当前值，0是acc的初始化值
表示从第一个数组中的数字加到最后一个