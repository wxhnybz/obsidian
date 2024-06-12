vue是一个前端渲染模型，只在初始化的时候，从服务器中获取了所有页面js，后续前端更改，直接调用获取的js

v-model作为双向绑定指令也是vue两大核心功能之一，使用非常方便，提高前端开发效率。在view层，model层相互需要数据交互，即可使用v-model。

v-model主要提供了两个功能，view层输入值影响data的属性值，data属性值发生改变会更新view层的数值变化。

父子组件之间的双向绑定
DOM元素上双向绑定
第二种场景分两个方向：

改变数据时通知视图更新：
vue初始化时会进行依赖收集，通过Object.definedProperty()的getter收集某个属性的所有依赖，然后通过Object.definedProperty()的setter在某个属性更新时通知视图更新。
视图改变时通知数据更新：
通过监听表单元素的input事件，从而通知数据更新。
你会发现vue-model只能用于input、textarea这些表单元素。根本原因是div、span这些普通的DOM元素的“值“发生变化时，vue没办法监听到。
