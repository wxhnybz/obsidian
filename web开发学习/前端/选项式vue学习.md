下属知识点
[[组件的生命周期]]
[[Slot插槽]]

#计算属性
计算属性值会给予其响应式以来被缓存，一个激素那属性仅会在其响应式以来更新时才会重新计算。
#方法
方法调用总是会在重新渲染时再次执行函数
#class属性
class本身自己可以指代一个属性,但是同时也可以使用绑定:class可以同时绑定多个属性,再结合css可以分块进行渲染
class绑定上可以是一个数组，数组中可以放一些相关的属性
同时可以使用一个数组嵌套对象，
#侦听器
再watch侦听器中，需要函数名与侦听的数据对象保持一致，可以在这里放置当数据改变时需要执行的函数
#组件的嵌套功能
![[Pasted image 20230921153356.png]]
#开发逻辑
vue以组件开发，组件之间可以随意嵌套
#全局注册
![[Pasted image 20230922100830.png]]
影响长期的维护
#组件之间传递数据
一种常用的方法式props，规定上需要与data同级别，用一个数组进行存储数据，props传递数据只能从父级传递到子级。可以传递任何数据类型。但是props可以通过函数的调用来进行子级传递到父级。
prop是只读的
#组件事件
当我们想要子组件传递到父组件的时候，使用$emit。这样我们传递回去的是一个事件，但是当父亲组件触发的时候就会传递相应的数据
组件之间的传递数据的方案，父传子，props；和子传父，自定义事件
#组件事件配合v-model使用
通过定义父亲界面函数，该函数可以通过传递参数来改变父亲界面中的数据信息，将该函数传递到子界面中，通过子界面事件的修改，函数的调用或参数的传入来进行信息修改操作。
#透传属性
透传属性是指在一个父亲页面中，规定的css，class或id的嵌套在子页面中就会透传下去，可以在子页面中进行设置属性为false阻断，（对比scoped，其只能使本页面的css作用，而不能作用在其他页面，没有阻隔作用）
