## 常用API
```
let map = new Map()
%% 插入 %%
map.set('age',18)
map.set('name','yxc')
%% 查找 %%
map.get('name')
map.has('name')
%% 访问大小,这是一个属性 %%
map.size
%% 删除 %%
map.delete('key')
%% 清空 %%
map.clear()
```
遍历map
for (let \[ key,value\] of map ){
console.log(key,value)
}
map.forEach(function(value,key){
console.log(key,value)
})


## set部分
set 一般使用来查重的,一般是用来作为哈希表的
```
插入
set.add('yxc')
set.add(18)
set.add(()=>{
console.log('hhh')
})
删除
set.delete(18)
查找
set.has(18)
%%  函数判断相等是比较是不是同一个函数
%%  清空函数
set.clear()

```