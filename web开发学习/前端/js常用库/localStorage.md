## 存到用户浏览器中的信息
类似于map之类,相比于cookie存的更大,更久
```
%% 存储一个信息 %%
localStorage.setItem('name','yxc')
%% 查找一个信息 %%
localStorage.getItem('name')
%% 删除一个本地信息 %%
localStorage.removeItem('name')
%% 清空本地浏览器信息 %%
localStorage.clear()
```

## 关于存放数据
后端server{
云盘
mysql
redis
}

前端{
内存
localstorage

}