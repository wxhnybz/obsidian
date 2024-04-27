redux的一个作用是独立于dom树之外，存放一些全局变量。这样dom树在修改变量的时候直接与全局模块进行交互。 

每一个第一个节点有一个函数（reducer），传入一个参数，设置一个新的state的值

reducer可以修改当前节点。这是一个递归遍历的过程，深度优先遍历。从根节点开始完整地遍历每一颗子树。

如果修改树中的某一个值，就将会将整个树重新计算一边。
修改的方式是通过dispatch()函数，这里的参数是一个对象。
这个对象是一个action，action是一个字典，通常有一个type键。

传入type=e之后，每一个reducer都会判断是否与其对应。如果匹配就会修改。如果不匹配，就会进行相应的修改。
a
bcd
ef

# 基本点redux
store：存放树结构
state：维护数据，通常维护成树的结构。
reducer：队state进行更新的函数，每个state绑定一个reducer传入两个参数：当前state和action返回新的state
action：一个普通对象。存放reducer传入餐宿，一版描述队state的更新类型。
dispatch：传入一个参数action队整棵树操作一遍

# 原生redux食用
通过构造reducer函数，然后构造根部的reducer函数，通过传入一个字典，将所有reducer包含进来构造子节点。
最后通过action.type判断需要在哪里使用dispatch函数修改state的值
# react-redux
provider组件，需要传入参数store属性
connect(mapStateToProps, mapDispatchToProps)函数：用来将store与组件关联起来。
mapStateToProps：每次store中的状态更新后调用一次，用来更新组件中的值。
mapDispatchToProps：组件创建时调用一次，用来将store的dispatch函数传入组件。

```
import React, { Component } from 'react';
import { connect } from 'react-redux';
class String extends Component {
    state = {  }
    render() {
        return (
            <h3>String:{this.props.string}
            </h3>
        );
    }
}
const mapStateToProps = (state,props) => {
    return {
        string: state.string
    }
}
// 组装组件
export default connect(mapStateToProps)(String);
```
这里函数是把state.string绑定到props的string属性中,然后拼接后返回。
调用完成dispatch函数之后，connect函数就会重新渲染