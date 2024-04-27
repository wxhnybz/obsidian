## Jquery
选择器
$() 基本上和css的选择器相同or类似
```
    // 这是jquery的一个基本的写法。
    let $div = $('div');
    console.log($div);
    $div.on('click.name1',function(){
        console.log('click this block');
        $div.off('click.name2');
    })
    $div.on('click.name2',function(){
        console.log(' this block');
    })
// 一个实例绑定了多个事件，使用名字区分来进行解绑特定的事件
```
  
    <div><a href="http://127.0.0.1:5500/usualport/jquery.html" target="_blank">acwing</a></div>
    应为a标签位于div标签之内，所以点击a标签的时候同时会点击到div，这是一个事件的向上传递，我们不希望这个发生，需要将a标签绑定事件触发，e ,使用e.stopPropagation

而相对的有，e.preventDefault，就是阻止当前的事件的操作，并不会影响父标签的额触发条件。