```
deleteDoctor({ uids: deleteuserList.value }).then(fetchUsers())这里fetchusers为什么不能加()
```

在这段代码中，`then`方法接收一个函数作为参数，这个函数会在Promise解析完成后被调用。如果你写`fetchUsers()`，那么`fetchUsers`函数会立即执行，而不是在Promise解析完成后执行。

如果你想要在Promise解析完成后执行`fetchUsers`函数，你应该传递函数本身，而不是函数的执行结果。所以，你应该写`then(fetchUsers)`，而不是`then(fetchUsers())`。

如果你需要传递参数给`fetchUsers`函数，或者需要在Promise解析完成后执行多个操作，你可以传递一个箭头函数给`then`方法，如下所示：
```
deleteDoctor({ uids: deleteuserList.value }).then(() => {
    fetchUsers();
    // 其他操作...
});
```