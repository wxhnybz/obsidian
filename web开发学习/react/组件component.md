react 返回时只能返回一个标签，通常用一个div括起来
```
 styles = {
        width: "100px",
        height: "100px",
        backgroundColor: "lightblue"
    }
    render() {
        return(
        <React.Fragment>
            <div style={this.styles}>{this.toString()}</div>
            <button className='btn btn-primary m-2'>left</button>
            <button className='btn btn-success m-2'>right</button>
        </React.Fragment>)
    }
```
外面这层大括号表明是一个表达式，里面这层大括号表明是一个对象

react是数据驱动型的，只要虚拟dom树中的一个值发生变化，就会执行一边所有有关于这个值的函数，递归开始。好了，这时候就会和真实的dom进行比较，不一样的话，render函数就会重新渲染。

map进行索引的时候，需要在div中添加key来进行索引，每一个标签都需要定义一个唯一的key

# React的数据绑定
由于js是非响应式的，我们想让数据实时变化，需要使用setState函数将数据绑定


## 编程语言特性
A&&B
当A是false的时候，就直接返回了，不会再判断B了
如果全都是true表达式，就会返回最后一个true表达式
如果是true&&abc就会返回abc
false有很多中，0，null，空

A||B
如果全都是false就会返回最后一个语句


## css
React的css需要使用小驼峰写法，同时都需要加上引号


## React的组件之间传递信息
```
  render() {
        return (<React.Fragment>
            {this.state.boxes.map(box => {
                return <Box key={box.id} x={box.x}>
                    <h1>Title</h1>
                    <p>Content</p>
                </Box>
            })}
        </React.Fragment>);
    }
```

返回的是this.props,其中里面的children包裹着h1和p两个标签

在一个对象里，setState 的key和value一样可以省略其中一个

# 函数组件
当我们发现当类组件中没有state属性的时候，我们就可以将类组件改写为函数组件（无状态的函数组件），简称为sfc
函数组件中只有一个render函数，直接return就好，函数组件直接通过props参数进行传递信息
```
const NavBar = (props) => {
	return (
	 <nav className="navbar bg-body-tertiary">
	  <div className="container-fluid"> 
	  <a className="navbar-brand" href="/">Navbar 
		  <span>Boxes Count: { props.boxesCount}</span></a> 
		  </div> </nav> );
}
 export default NavBar;
```

## 关于函数组件中的对象的解构
```
const Boxes = ({boxes,onReset,onDelete,onClickLeft,onClickRight}) => {
    return ( <React.Fragment>
        <button onClick={onReset} style={{marginBottom:"15px"} } className='btn btn-info'>Reset</button>
        {boxes.map(box => {
            return (
                <Box
                    key={box.id}
                    box={box}
                    onDelete={() => onDelete(box.id)}
                    onClickLeft={() => onClickLeft(box.id)}
                    onClickRight={() => onClickRight(box.id)}>
                    <h1>Box:</h1>
                    <p>#{box.id}</p>
                </Box>)
        })}
    </React.Fragment>) ;
}
```
通过对象的结构
const {name : nm, age} = person;  // nm是name的别名
将父组件定义的方法和参数传递到子组件中

# 组件生命周期
mount 挂载周期 constructor() -> render() -> componentDidMount()
update 修改周期 render() -> componentDidUpdate()
unmount 删除周期 componentWillUnmount()

mount 挂载周期
```
 componentDidMount() {//mounted函数
        console.log('app - mounted')
        ajax()
        this.setState({})
    }
```
渲染完成之后想数据库中发送请求，进行数据挂载
## mount
	render函数也会在其子组件中进行递归操作，返回所有的子组件执行周期

	只有当所有的子组件，组件都constructor和render之后才会继续递归mount函数

## update
	当一个state中发生变化的时候，会从修改元素的虚拟dom树位置向下递归执行render函数

时延主要发生在渲染真实的dom树中，在内存中的dom树并不会耗费太长时间

```
 componentDidUpdate(prevProps, prevState) {
        console.log('navbar - updated')
		if(prevState.boxes[0].x!==this.state.boxes[0].x){
		ajax()}        
        console.log('prevState', prevState)
    }
```
上面这段代码的意思是，现在前端进行渲染改变，只有当数据和数据库中的内容不一样的时候再向后端发送数据请求。提高的响应速度。
2. 上面代码的意思是，先进行前端的修改，update周期比对后再进行像后端传递参数
## unmount
删除之前可以做一些清理，可以进行更新一下全局变量