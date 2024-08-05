useState 就是设置状态参数，并且根据setCount等修改状态的函数进行修改。
useRef 传入响应式变变量
useEffect 这个有意思
useMemo 缓存计算函数
### 连接到外部系统
有些组件需要与网络、某些浏览器 API 或第三方库保持连接，当它们显示在页面上时。这些系统不受 React 控制，所以称为外部系统。请在组件的顶层调用 `useEffect`：(setup函数和depnedency选项，一种diff比较依赖项)
setup函数应该返回一个清理函数，将所有的连接进行清空。

