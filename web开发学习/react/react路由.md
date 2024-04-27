web页面分为静态页面和动态页面
动态页面又分为前端渲染和后端渲染。
route是为了让每一个前端页面开起来假装和后端渲染模式是一样的

# 路由中通过url传递参数
```
这是 `react-router` 的一种路由参数的写法。在 URL 路径中，`:` 后面的部分被视为一个参数的名称。当你访问一个匹配这个路径的 URL 时，这个参数的值会被设置为 URL 中对应的部分。
```

```
1. `export default (props) => { ... }`: 这是一个默认导出的匿名箭头函数，它接受一个 `props` 参数。在React中，函数组件接受一个 `props` 对象作为参数，其中包含了传递给组件的属性。
    
2. `<WebContent {...props} params={useParams()}></WebContent>`: 这里使用了JSX语法来渲染一个名为 `WebContent` 的组件。`{...props}` 语法表示将外部传入的 `props` 对象中的所有属性解构并传递给 `WebContent` 组件。而 `params={useParams()}` 则是将 `useParams()` hook 的返回值作为 `WebContent` 组件的一个名为 `params` 的属性传递进去。
    
3. `useParams()`: 这是React Router库提供的一个hook函数，用于从当前URL中提取参数。当你的组件被包裹在`<Route>`组件中时，`useParams()`可以帮助你获取当前URL中的参数，并将其提供给你的组件使用。
    
因此，这段代码的作用是将外部传入的 `props` 对象中的所有属性以及当前URL中的参数传递给 `WebContent` 组件。
```

# 路由匹配
路由匹配只匹配到？前面的部分，并不匹配到？后面的部分。剩余的就作为参数传输了

路由访问的两种方式，
第一种是通过 /: 参数的方式来进行 useparams.参数
第二种是通过？参数的方式  usesearchparams[0].get('参数')

# 重定向
如果说页面不存在就重新定位到404，使用通配符
```
  <Routes>
	<Route path='/' element={<Home/>}></Route>
	<Route path='/linux' element={(<Linux/>)} ></Route>
	<Route path='/django' element={<Django/>} ></Route>
	<Route path='/web' element={<Web />}></Route>
	<Route path="/web/content" element={<WebContent />}></Route>
    <Route path='/404' element={<Notfound></Notfound>}></Route>
	<Route path="*" element={<Navigate replace to="/404"/>}></Route>
  </Routes>
```
这就是一个短路方式，从上向下匹配，如果匹配到的话就直接返回。所有都没有匹配到的话就重定向的404

# 嵌套路由
```
<Route path='/linux' element={<Linux />} >
 <Route path='homework' element={<h4>Linux Homework</h4>}></Route>
<Route path='terminal' element={<h4>Linux Terminal</h4>}>
</Route>
```
这种的话路由会自动拼接到一起，等价于/linux/homework
我们在子组件中这样使用outlet来进行渲染子路由
`<Outlet />` 是 React Router v6 中的一个组件，它用于渲染当前路由的子路由组件。

当你在一个路由组件中使用 `<Outlet />` 时，React Router 会查找当前路由的子路由，并将匹配的子路由组件渲染在 `<Outlet />` 的位置。

# 路由查询参数
```
import React, { Component } from 'react';
import { useParams } from 'react-router-dom';
import { useSearchParams } from 'react-router-dom';
import { Link } from 'react-router-dom';
const WebContent = () => {
    console.log("hooks", useSearchParams())
    const id = useSearchParams()[0].get('chapter')
    const sec = useSearchParams()[0].get('section')
    console.log(id,sec)
    return (
        <React.Fragment>
        <h1>Web-{id}</h1>
            <div>内容-</div>
            <hr />
        <Link to='/web'>返回</Link>
        </React.Fragment>
      );
}
export default WebContent;
```