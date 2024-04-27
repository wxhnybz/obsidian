设置一个定时器触发
setInterval ,setTimeout都有一个返回值，
返回值是一个number类型，表示当前定时器的唯一ID

取消定时器的API
clearInterval(func_id)就是将func_id清空，将定时器取消

代码块
```
let func_id;
$div.on('click',function(){
if(func_id) return false;
func_id = setInterval(function(){
	console.log('timer')
},2000)
}

$div.dblclick(function(){
clearInterval(func_id)
})
```

