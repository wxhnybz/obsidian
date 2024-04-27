## jQuery的选中标签
类似于CSS选择器
```
let $div = $('div')
let $div = $('.big-div')
let $p = $('div > p') 表示选中div标签内的p子标签
//像这种使用$命名，就是表示是通过jQuery的方式来选中绑定一个标签
```


## jQuery进行绑定事件
```
$('div').on('click',function(e){
console.log("click div")
})
```
当存在多个相同类型的事件触发函数的时候通过click.name来区分
```
$('div').on('click.first',function(e)){
console.log('click div')
$div.off('click.first')
}
```

## jQuery的return
return false 就是同时阻止事件的发生和阻止事件的透传
```
e.stopPropagation()：阻止事件向上传递
e.preventDefault()：阻止事件的默认行为
```

## jQuery对元素的隐藏展现
```
隐藏元素，参数表示消失的时间
展现元素
$A.hide()
$A.show()
慢慢消失，参数表示消失或者出现的时间
$A.fadeOut()
$A.fadeIn()
```
## jQuery对于元素，类和CSS的操作
#### 构造一个标签
```
let $a = $('<a href="https">内容</a>')
```
#### 在内容里的标签进行添加或者删除操作。
```
$div.append($a) 插到末尾
$div.prepend($a) 插到开头
$A.remove() 输出元素$A
$A.empty() 清空元素$A的所有的儿子
```

构造标签是比较灵活的，可以进行多层嵌套。需要使用到js中的连续字符串为\`\`这个符号
构造标签的html页面可以添加多个属性，定义id，类型和style等


## 直接对类进行操作
```
$div.addClass    绑定一个类
$div.removeClass 解绑一个类
$div.hasClass    判断有无一个类
```


## 直接对CSS进行操作
```
//直接传输一个对象进行修改CSS
$div.css({
width:
hight:
'background':'',
})
```


## 直接对属性进行操作
```
$div.attr('id','')将id属性修改为一个新的属性
$div.attr('class','')将class属性修改为一个新的属性
$div.attr('yxc')就是查询访问yxc这个属性。

```

## 对HTML内容，文本的操作
$a.html()获取、修改html内容
$a.text() 获取、修改文本信息
$a.val()  获取、修改文本的值
对于一些输入的内容可以通过val来改变值，同时也可以预先设置字体的颜色。


## jquery查找方法
```
$div.parent(s),查找父亲节点或查找祖先节点
$div.children('div')，查找孩子节点
$div.find('div') ，查找所有的子节点
```

## 额外的函数
#### ajax的get和post
**在不刷新页面的时候，获取服务器的某些数据**
获取的信息，我们再在服务器中进行拼接出来。
*获取一个页面，为get方法，一般是从服务器中获取数据的*

```
$.ajax{
url: url
type:"GET"
data:{}
dataType:"json"
success: funtion(resp){

}
}
```